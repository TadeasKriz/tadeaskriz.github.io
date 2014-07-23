---
title: The first usable version of Torch
---
This weekend was hectic, but I've finally managed to get [**Torch**][1] into usable form. However there is no way to delete entities from database and there is no documentation yet. Also there are just a few tests written, but more will come in the upcoming two weeks.

## Current status

Loader and Saver API should be fully usable (except async operations). You can save any entity and then also load them back. Loader API allows you to filter, order and limit results. The API is completely fluent and immutable, guiding you through the query creation. Each step implements **Iterable** interface, so you can use it in `foreach` loops. That way the data will get loaded when they're needed and not all at once. Also you can call `list()` method to get all the results in one `List`.

## What's next

I need to implement the async API. It'll work in a way that each callback is run on **UI thread**, so you don't have to worry about direct modification of your UI. Then I'll implement the Deleter API, so there's an easy way to delete entities. Last but not least, tests. I should write a lot of tests to cover all the APIs to ensure proper  behavior.

## Change of alpha release date

More projects came into scope, which has higher priority than releasing alpha version of [**Torch**][1]. Because of that, I have to shift the alpha release date. If everything goes well, the alpha should be out at the end of November.

## Where to get latest version

Latest version can be found [here][1]. Until further notice, this is always the bleeding edge and it's not considered stable!

[1]: https://github.com/brightify/torch/tree/develop
