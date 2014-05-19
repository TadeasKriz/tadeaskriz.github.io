---
title: Actual generic parameters of a Class<?> in runtime
layout: post
author: Tadeas Kriz
---

Yesterday I was working on dynamic mapping of marshallers to their marshalled type. The way I've done it was having an interface `Marshaller` with generic parameter `<T>`. Then I'm using **Reflections** to get all classes that implements this interface. Then I need to get the actual type ot `<T>`, which is a problem if there is for example an abstract class, that is the base for all marshallers. So if you have the following setup, it's not as easy as just calling `ParameterizedType#getActualTypeArguments()".

```java,1
interface Marshaller<T> { 
	... 
}

abstract class AbstractMarshaller<T> implements Marshaller<T> {
	...
}

class BooleanMarshaller extends AbstractMarshaller<Boolean> {
	...
}
```

So I have written the following method, that resolves actual types of all generic parameters of a given class.

```java,1
public Map<TypeVariable, Type> params(Class<?> targetClass, Class<?> cls, ParameterizedType type) {
    TypeVariable[] parameters = cls.getTypeParameters();
    Type[] actualParameters;
    if (type != null) {
        actualParameters = type.getActualTypeArguments();
    } else {
        actualParameters = parameters;
    }

    Map<TypeVariable, Type> map = new HashMap<TypeVariable, Type>();
    for (int i = 0; i < parameters.length; i++) {
        map.put(parameters[i], actualParameters[i]);
    }
    if (cls == targetClass) {
        return map;
    }

    List<Type> genericParents = new ArrayList<Type>();

    Type[] genericInterfaces = cls.getGenericInterfaces();
    Type genericSuperclass = cls.getGenericSuperclass();

    Collections.addAll(genericParents, genericInterfaces);
    genericParents.add(genericSuperclass);

    for (Type genericInterface : genericParents) {
        ParameterizedType parameterizedInterface = (ParameterizedType) genericInterface;

        Map<TypeVariable, Type> genericInterfaceMap = params(targetClass,
                                                             (Class) parameterizedInterface.getRawType(),
                                                             parameterizedInterface);
        if (genericInterfaceMap != null) {
            for (TypeVariable key : genericInterfaceMap.keySet()) {
                Type value = genericInterfaceMap.get(key);
                if (value instanceof TypeVariable) {
                    genericInterfaceMap.put(key, map.get(value));
                }
            }
            return genericInterfaceMap;
        }
    }
    return null;
}
```

And you'd use it like so:
```java
Map<TypeVariable, Type> params = genericParameters(Marshaller2.class, BooleanMarshaller.class, null);
```
And the `params` map would have exactly one entry, `(TypeVariable) "T" => (Class) Boolean`.

I wrote this because I was unable to find the solution anywhere, so hopefully this will help someone in the future.


PS: The method needs some refactoring for sure and I will do it in the following days.
