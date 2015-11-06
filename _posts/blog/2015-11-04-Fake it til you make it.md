---
layout: post
title: "Fake it til you make it!"
modified:
categories: blog
excerpt: "Why fake people are better than real people."
tags: [Flatiron, Pair Programming]
image:
  feature: bg-2.jpg
date: 2015-11-04T08:00:00-04:00
share: true
---
<iframe src="//giphy.com/embed/TxjAakMUtgPN6" width="480" height="366" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>
You've just finished your program, or at least your minimum viable product...or have you? 

An important part of any good program, or project for that matter, is testing. It lets you know that the piece of code you've poured your blood, sweat, and tears into actually does the thing you told your manager it would do. However, testing requires **data**, oodles of it. 

###Get that data
Where are you going to get all that data? It's not like there's a ruby gem that randomly generates oodles of data. Actually there is. It's called [Faker](https://github.com/stympy/faker). The Faker gem is a port of the popular Perl Data::Faker library and it generates some awesome fake data. 

###I love fake data, but I'm a discerning consumer, tell me more.
You can use Faker to make fake names, emails, addresses, cities, street names, secondary addresses, building numbers, zipcodes, time zones, postal codes, countries, bitcoin addresses, credit card numbers, isbns, colors, departments, logos, dates, ip addresses, lorem ipsum, numbers, decimals, phone numbers and many more. All of these can be generated with a simple bit of code like:

<script src="https://gist.github.com/Gilmoursa/059db30b5a2520b079c3.js"></script>

I bet you never knew fake data would look so real. Well guess what it does and Faker is easy to implement, just follow these simple steps and you'll be on your way to generating tons of new aliases for yourself. 
<figure>
	<img src="http://investorplace.com/wp-content/uploads/2014/02/bacon.jpg">
</figure>

###Let's start fakin'...rhymes with bacon

- Add it to your `GemFile`
- run `bundle` or `bundle install` if you've got key strokes to burn.

Open your ruby project and create a file called `seeds.rb` inside `db/migrate/seeds.rb`. This file is where you'll configure your fake information. Think of it like a factory of fake data. Inside here you'll want to first clear your current data if you have any left over from a previous session of testing. *Why?* The old data may not mesh with your current parameters. For example, perhaps you've added a `topping` to your `Sandwich` model. Any old data you've created will have a value of `nil` for it's `topping` parameter. In Rails, deleting this information is as easy as `Sandwich.destroy_all`.

Now that we're working with a clean slate. Let's make some data. I like to use another gem called [Fabrication](http://www.fabricationgem.org/). It's great for generating objects in Ruby.

###Fabrication...doesn't rhyme with bacon
- Add it to your `GemFile`
- run `bundle` or `bundle install` if you've got key strokes to burn.

Now let's pair **Fabrication** with **Faker**. To generate 300 fake people we must first create a recipe for our fake person. The person below has a name, email, and password. Pretty straight forward. Take a look.
<script src="https://gist.github.com/Gilmoursa/22ce989e0045a8cb2c56.js"></script>

Generating 300 instances of this fake person, each with their own unique hopes and desires, or at least names and email addresses is even easier. Just run this `300.times {Fabricate(:user)}`

