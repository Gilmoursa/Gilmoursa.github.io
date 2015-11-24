---
layout: post
title: "We Didn't Start the Fire"
modified:
categories: blog
excerpt: "Generating in Ember"
tags: [Flatiron, Ember, Javascript]
image:
  feature: bg-1.jpg
date: 2015-11-23T08:00:00-04:00
share: true
---

###Generators
EmberJS, like Ruby on Rails contains many tools to help build great web applications in a relatively small amount of time. Ember accomplishes this in much the same way Ruby on Rails does, through generators.

If you're familiar with Ruby on Rails, then you know that you can create models, migrations, and other Rails objects with a simple command in the terminal like `rails generate model Product` or `rails g migration AddPartId`. In this blog post we'll learn about these same generators in an Ember context.

###Generating Ember "Blueprints"
In Ember we call these generatable objects ["blueprints"](http://www.ember-cli.com/extending/). There are many such blueprints that you can generate, but we'll focus on just three: routes, models, and templates. To see all the "blueprints" you can generate in Ember, type `ember generate --help` or `ember g -help`. `g` is an abbreviation for `generate`.

###Generating Ember Routes
Generating a route creates 3 files and make changes to the router. Let's look at an example. Typing `ember g route hamburger` will create a `app/routes/hanburger.js`, `app/templates/hamburger.hbs`, and `tests/unit/routes/hamburger-test.js`. You'll see a short summary displayed in the terminal following the command you typed. In short, a generated route will include the route itself, a template, a test, and the route will be registered in the router.

####A Route
An empty route will look like this:
<script src="https://gist.github.com/Gilmoursa/7a25126dc50586fa0e23.js"></script>

####A Template
An empty template will look like this:
<script src="https://gist.github.com/Gilmoursa/6f823a3ab98b11c00ad8.js"></script>

###Generating Ember Models
Generating a model by typing `ember g model name` will create two files: a model and a test. 

####A Model
A basic model might look like this:
<script src="https://gist.github.com/Gilmoursa/355e67ef3e0a45dd1f08.js"></script>

###Generating Ember Controllers
Typing `ember g controller name` will generate two files: a controller and a test. The controller file while empty isn't much to look at, but it can contain things like possible states, computed properties, and actions.

####A Controller
Here's an empty controller, the space between the brackets could contain functionality such as the examples mentioned above.
<script src="https://gist.github.com/Gilmoursa/52fe1688d8c0ced0736b.js"></script>


   | Component | Controller | Model | Resource | Route | Template
 :---: | :---: | :---: | :---: | :---: | :---: | :---: 
 component | controller | model | model | route | template 
 test | test | test | route | test | 
  | | | | template | *registers router | 
  | | | | test |  | 





  
