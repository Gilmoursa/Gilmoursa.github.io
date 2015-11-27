---
layout: post
title: "Ruby on Rails Request Response Cycle"
modified:
categories: blog
excerpt: "Routers, Controllers, Views, and more"
tags: [Flatiron, Ruby, Ruby on Rails]
image:
  feature: bg-4.jpg
date: 2015-10-10T08:00:00-04:00
share: true
---

###Rails Framework
Ruby on Rails is the most popular Ruby framework and for good reason. It gives you a large amount of control while also giving you a ton of built in tools and files to work with. To properly make use of these tools, however, you must learn the request response cycle. 

###Interacting with Websites
Websites and your browser engage in a delicate dance of requests and responses. As a user you interact with your browser which makes these requests on your behalf. When you navigate to a new page, that's a request. When you submit a form that's a request. 

There are two main kinds of requests, POST requests and GET requests. POST requests are when you provide information to the website. You are POSTing information to the site. An important takeaway about POST requests is that they update the database. In the example above, submitting a form is a type of POST request. The contents of the POST request are eventually saved to the database. When you view a diffent page on the site, and you ask the website to give you the information contained in that page, you are submitting a GET request. You want to GET that information.

###How do Requests work?
Let's start at the beginning. You open your browser and enter a URL. The browser sends a GET request to the URL. The GET request hit's the Rails router (`config/routes.rb`). You can think of the router as an old-fashioned switchboard operator connecting your call with the person you're trying to call. The router looks through the routes file and connects you with the correct controller.

####Controllers
A controller is a list of instructions. It exists between the request and the response, for example, some sort of view (more on views later). The router will direct you to the right controller and then the router's job is done. The controller, then directs the request to the correct action. There are seven actions:

 - index - GET which shows all of whatever resource (blog posts, images, students)
 - show - GET which shows a selected resource (the 5th student, the 2nd image)
 - new - GET displays the form to make a new resource
 - create - POST saves a new resource
 - edit - GET show the form to make changes to a selected resource
 - update - POST saves changes to a selected resource (notice the distinction between this and edit)
 - destroy - deletes a given resource 

Once the action is completed, the action will direct you to a response of some kind. This could be HTML or JSON.

####Views 
 Views are like templates or layouts for what a page will look like and display to you. A view is composed of html and erb. Erb is embedded Ruby and it's a way of injecting ruby code into html pages Erb elements will be wrapped in `<%` `%>` tags or `<%=` `%> if you want the code to be visible. 

 The HTML will format the various ruby components, such as putting a Ruby variable inside an `<H3>` tag or iterating through a set of data using the `each` method and formatting each item within `<li>` tags.

###Request Response Example
Let's say we visit a website, `www.myphotos.com`, a Ruby web application. You type the URL into your browser. The browser sends a GET request to the `routes.rb` file.

####Viewing an Index Page
In this example, the index page routes you to a  photos controller with an `index` action. This action finds all the photos and sends you to a view `www.myphotos.com/photos` which renders a file `index.html.erb` that iterates through all of your photos and formats them with some html.

####Viewing a form
You want to add an additional photo so you click on a link to "add new photos". This submits another GET request to the router which connects to the `/photos/new` path in the photos controller which directs you to a form to submit a photo. You type in some information and upload a photo. At the bottom of the page you click "submit".

The form submits a POST request, because this time instead of asking for information *from* the website, you're sending information *to* the website. The post request will go to the server then router then photos controller and finally the `create` action. The `create` action will take the information from the form and save it into a new photos object in the database. After the new photo is saved the action will redirect to a view, in this case showing your newly uploaded photo. An action only redirects when it's instructed to, for example `redirect_to @photo` The html from the view will be rendered by your browser.





















