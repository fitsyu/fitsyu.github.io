---
title: swagger-and-mockaroo-combo
date: 2019-09-20 23:07:27
tags:
---



For your information, we can combine the power of API design using Swagger with realistic mock data using 
Mockaroo.

Here is how we can do that.

So for the sake of demonstration, we assume we have an endoint to get list of point of interest (POI).

The design in Swagger spec would look simply like this.

```YAML
paths:
    get:
        parameters:
        responses:
```

Yes, in Swagger it self we can return mocked response. 

But the thing is it is not REALISTIC. 

Because it would be derived from example from the definition.

Here is where REALISTIC mock data from Mockaroo can join the game.

So let's recrete the definition for the response in Mockaroo:

1.

2.

Now we have live links from Mockaroo.

Here is how to use it in swagger.

Set server to <base url from mockaroo>

And some settings here and there


Now let us try to use the cool TRY IT feature from Swagger.

Now the benefits are that the users of our API can learn the API more naturally with those realistic responses.

That is the trick.

Glad if can be helpful.

Nice to share this with you guys.

Thanks for listening.