---
title: My first opensource project
---
I'm currently working on my first opensource project, with codename [**Torch**][1]. It's an Android ORM framework which is built to have similar API to [**Objectify**][2]. I've never worked on anything opensourced until I got a job in Red Hat, but I think I should radically change that and contribute to the community. That's why there will be more opensource libraries from [Brightify][3], so keep tuned for more.

### What's an ORM

ORM means [Object-relational mapping][4] and it's a great way to easily persist data in your application. You don't need to write your own code to handle database connection, to create tables and to load/store the data. It sounds great, right? Well, there is one drawback and that's performance. I have not measured the performance of **Torch** yet, but from what I know about reflection, it might be an order of magnitude. However that mainly applies to performance sensitive applications and thus it depends on the scenario. If you're writing application, in which handling the database would increase the development time a lot, you should try using an ORM framework. Also there is another one big advantage and that's stability. When you write your own database handling code, it might contain bugs which might be easily overlooked. Don't get me wrong, I'm not saying that ORM frameworks are completely bug-free, but it's less likely to happen if you'll pick a stable release. 

### Another ORM? Why?

I've tried many Android ORMs, but every single one has something I didn't like. Some had the requirement to extend some abstract classes, some seemed too heavyweight for what I needed and none of them was quite like **Objectify**, which I've used on Google AppEngine and totally fell in love with. So I've decided to write my own ORM which would have similar API as **Objectify** and that's how **Torch** project was born.

### Current status

Right now, there are many features missing and it's definitely not usable yet. But I'm working hard to release first alpha preview very soon. By soon, I mean the end of this month (October 2013). The first alpha preview will still not be ready for production, that's for sure. And it won't become a beta until I'll use it in at least two project myself. After I'll test it in real environment, I'll be finally able to say that the API won't change and make it a beta. Then again, it'll need more testing, possibly from the community. There won't be a stable release until I feel like it's ready.

[1]: http://github.com/brightify/torch
[2]: https://code.google.com/p/objectify-appengine/
[3]: http://brigtify.org
[4]: http://en.wikipedia.org/wiki/Object-relational_mapping
