---
layout: post
title: "Fake it til you make it!"
modified:
categories: blog
excerpt: "Why fake people are better than real people."
tags: [Flatiron, Objects, Ruby, Faker, Fabrication]
image:
  feature: bg-2.jpg
date: 2015-11-04T08:00:00-04:00
share: true
---
<iframe src="//giphy.com/embed/TxjAakMUtgPN6" width="480" height="366" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>

An important part of any good program is testing. Testing lets you know that the piece of code you wrote actually works the way you intended it to work. However, testing requires **data**, lots of it. 

###Generating Data
[Faker](https://github.com/stympy/faker) is a Ruby gem that will help you create random iterations of data within the parameters you specify. The Faker gem is a port of the popular Perl Data::Faker library and it generates some incredible fake data. 

###Kinds of fake data available
You can use Faker to make fake names, emails, addresses, cities, street names, secondary addresses, building numbers, zipcodes, time zones, postal codes, countries, bitcoin addresses, credit card numbers, isbns, colors, departments, logos, dates, ip addresses, lorem ipsum, numbers, decimals, phone numbers and many more. All of these can be generated with a simple bit of code like:

<script src="https://gist.github.com/Gilmoursa/059db30b5a2520b079c3.js"></script>

I bet you never knew fake data would look so real. Faker is easy to implement, just follow these steps and you'll be on your way to creating tons of incredibly useful fake data to test your web application. 
<figure>
	<img src="http://investorplace.com/wp-content/uploads/2014/02/bacon.jpg">
</figure>

###How to create fake data

- Add it to your `GemFile`
- run `bundle` or `bundle install`

Open your ruby project and create a file called `seeds.rb` inside `db/migrate/seeds.rb`. This file is where you'll configure your fake information. Think of it like a factory of fake data. Inside here you'll want to first clear your current data if you have any left over from a previous session of testing. *Why?* 

The old data may not mesh with your current parameters. For example, perhaps you've added a `topping` to your `Sandwich` model. Any old data you've created will have a value of `nil` for it's `topping` parameter and this could throw an error. In Rails, deleting this information is as easy as `Sandwich.destroy_all`.

Now that we're working with a clean slate. Let's make some data. I like to use another gem called [Fabrication](http://www.fabricationgem.org/). It's great for generating objects in Ruby.

###Using the Fabrication gem
- Add Fabrication to your `GemFile`
- run `bundle` or `bundle install`

Now let's pair **Fabrication** with **Faker**. To generate 300 fake people we must first create a recipe for our fake person. The person below has a name, email, and password. Pretty straight forward. Take a look.
<script src="https://gist.github.com/Gilmoursa/22ce989e0045a8cb2c56.js"></script>

Generating 300 instances of this fake person, with their own unique names and email addresses is even easier. Just run this `300.times {Fabricate(:user)}`

