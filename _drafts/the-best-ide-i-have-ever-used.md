---
title: The best IDE I have ever used
tags: ide, visual studio, IntelliJ IDEA, android, Eclipse
---
Long time I've been comparing many development environments and now it's time to pick the best one. First I should say, that each of them I've basically used for different type of project. For example, Visual Studio for desktop Windows apps and Eclipse for Android apps. And because of that, the point of view might be a bit different, but I'll sum pros and cons of each single one.

### Visual Studio
Before any IDE, I've been using [**PSPad**][1] to write PHP scripts and sites. Switching to Visual Studio was a big change back then and I've fallen in love with that IDE very quickly. First Visual Studio I've used was the 2005 edition. Its code completion, **IntelliSense** was perfect and almost every time it helped me write the code faster and more effectively. Also the automatic code formatting is brilliant, works as intended and it's not interrupting you while writing.

#### Pros

* superior code completion
* fast and smooth
* simple and easy to use interface
* free Express edition

#### Cons

* expensive if Express edition is not enough

### NetBeans

It was the second IDE, I've used for quite a long time. I've used it for PHP development, but it supports many more languages like Java, C/C++ and more. First big advantage, it's free. For small business, Visual Studio might be too expensive and then NetBeans might be a good alternative. When I used it, it was on 4GB RAM computer and after a while, NetBeans was eating so much of the memory and I had to restart it. This bug (memory leak) migth be already fixed, but today, when developer's computer should have at least 8 Gigs, it's not really a problem.

### Eclipse

My first experience with **Eclipse** was when I started developing for **Android**. At that time, **Java** was new for me and I found it really difficult compared to C#. Because of that language difference, I didn't like Eclipse at the beginning, but the interface was also confusing and overall behaved worse than Visual Studio. It was slow and its **code completion** was not really helpful. Now, after two years working in Eclipse, I still think that it should help me more. But I got used to it and today, whatever I can, I develop in Eclipse. Whether it's Java, PHP and also C++. The biggest issue of Eclipse is, that it sometimes freezes. Well, to be honest, it's quite frequent. I understand, that it's auto-building the source in the background, but I'm used to hit **Ctrl+S** every few lines of code, just to be sure. With Eclipse, I often get nice dialog, saying that I have to wait until the auto-build is done. This is really frustrating. I know I could turn the auto-build off, but that's not what I want. It could just put my latest request to save the file at the end of queue, and save it after the build is done.

#### Pros

* completely free
* lot's of plugins/extensions
* supports many languages
* multiplatform

#### Cons

* written in Java => not the best performance
* memory-eating machine
* sometimes hangs

### IntelliJ IDEA

Because of working for Android, I was long time Eclipse user and I've never trusted any other IDE, that it would get the job done. Then Google released its [**Android Studio**][2] preview along with switching over to IntelliJ IDEA and build system Gradle. On their presentation it looked really lovely, so I've decided to give it a try. And I was really suprised how great the Android Studio was, but it was lacking a bit in one thing, which is it only supported Android projects. But I'd often need to write simple Java library or Java web application and that's something that Android Studio couldn't provide. And that was the time I've switched to IDEA and as of now I can't imagine better IDE for Java. It has great performance and seems to be learning as I type and making the code completion more precise.

#### Pros

* free community version
* can support multiple languages via plugins from JetBrains (JavaScript, PHP, HTML, Groovy etc.)
* great performance
* understands how the code should be written
* multiplatform

#### Cons

* there aren't many plugins (AFAIK guys from JetBrains break the API with each version)
* 


[1]: http://pspad.com
[2]: http://developer.android.com/sdk/installing/studio.html