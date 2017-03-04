---
layout: post
title: "Mock API for RESTful services"
permalink: mock-api-for-restful-services
date: 2017-03-02 09:54:45
comments: true
description: "mock api for restful services"
keywords: "api, rest, mock, services"
categories: "utilities, productive"

tags:

---

REST API is explained here. Link to the article on Postman.

[MockAPI](http://www.mockapi.io/ "MockAPI") is one such service that makes API mocking easy. It has a non nonsense UI that makes API mocking easy even for someone who has minimal technical skills. With a fair idea on how RESTful Webservices work, anyone can create mock API in 5 mins.

Register with the service by providing your name email and password. Alternatively you can login with your Github or Google credentials. Once logged in, you can add a mock project. These are the projects for which we are gonna expose APIs soon.  

Once the project is created, its time to create resources. Resources are so-and-so. Resources will be used to generate the endpoint for RESTful API. The form for creating resources is pretty self-explanatory. Once a resource is created, you can see an interactive page that displays the resource you just created with your first mock API URL displayed on the top. 

Hover on the resource and click to generate mock data. You can even view and update the mock data or update the resource definition. Once done, copy the mock API URL, replace :endpoint with the resource you've just created and start using it.

You can create multiple resources withing your project. Ofcourse, each resolves to a different endpoint. You can even create parent and children resources. This is best explained [here](http://www.mockapi.io/#/docs "Docs"). To connect a resource as a child to another resource, click on the node before the child resource and connect it with the node before the parent resource. Note that, when a parent child relation is established between two resources, the endpoints for the child resource will be changed.


