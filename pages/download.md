---
layout: page
title: How controllers are specified in the Swagger file
---

API Studio makes it easy for you to model and try out your API. When you're in the Studio, your API calls return simulated responses. When you're ready to implement the "business logic" of your API, a good approach is to download your API as a Node.js project. Then, you can implement "controller" files in Node.js to handle whatever work your API needs to do, such as making backend target requests. 

# What is a controller?

A controller is a Node.js file that executes when specified API paths are called. 

In the default "hello, world" API Studio project, you can see immediately how the controller is specified on the `/hello` path by looking at the project's Swagger file:

{% highlight yaml %}
    paths:
      /hello:
        x-swagger-router-controller: hello_world
        get:
          description: Returns greetings to the caller
          operationId: hello
{% endhighlight %}

The extension `x-swagger-router-controller` specifies the name of the Node.js controller file associated with the `/hello` path. And the `operationId` specifies the name of a function to call in that file when `/hello` is called.


# Download to a Node.js project

In API Studio, select **Download Node.js Project** from the Project menu. 

Your project is saved on your file system as a Node.js [swagger](https://www.npmjs.com/package/swagger) project. 

The downloaded project is based on the npm `swagger` module. The downloaded `swagger` project has a well-defined structure and includes a built-in Express server, a command-line interface, an editor (Swagger Editor), and more.

Under the /api directory, you'll find the `swagger` folder. This is where your project's Swagger definition file lives. It's called `api/swagger/swagger.yaml`. There's also an `api/controller` folder. This is where you'll implement the API's business logic -- in Node.js. 

# Next steps: Learn about npm swagger

To set up your local environment, you need to install the `swagger` npm module:

`npm -g install swagger`

With this module installed, you're ready to implement and test controllers on your local system.

Read more about using the `swagger` command-line interface and implementing controllers in the [swagger-node documentation](https://github.com/theganyo/swagger-node/tree/master/docs).
