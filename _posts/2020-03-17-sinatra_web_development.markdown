---
layout: post
title:      "Sinatra Web Development"
date:       2020-03-17 05:00:49 +0000
permalink:  sinatra_web_development
---


I had a lot of fun creating my Sinatra project. When coming up with a project, I thought through a couple of ideas: a dog-walking appointment service, a recipe aggregator, or a news site. 

At the time that I was coming up on thinking about my project, I finished a book I had been reading for quite some time and couldn't wait to share my thoughts with the world and simulteanously see what everyone else was thinking. I ultimately decided to create an application that would let me add books to a general library and review the books. Looking toward the future, I thought this project might be fun to expand on and potentially build recommendations into. 

Diving in, my MVC (models, views, controllers) application had three models: Books, Reviews, and Users. These three models inter-related with one another through several `has_many`, `belongs_to`, and `has_many, through:` relationships. I built four controllers, one for each model and an application controller. The user controller pointed a user to a view that showed them the reviews that belonged to them. The books controller let a user add books and see all reviews for that book. The reviews controller, the most sophisticated of them all allowed a user to create a review, edit their own review, view their reviews, and delete their reviews. A user couldn't delete or edit another user's review. 

The application controller gave my application the ability to sign users up, log them in, and authenticate users using the `has_secure_password` method. ActiveRecord and Sinatra give a lot of flexibility to build a sophisticated application. 

As a fun bonus, I also included a `flash[:message]` to prevent users from creating books that already existed in the database as well as one to prevent users from submitting blank reviews. I took advantage of some of the methods that we had learned to use as helper methods previously, like slugs, to give my application the flexibility to travel to see the reviews for books by their slugs. All in all, I enjoyed building this application and can see use for it for myself in the future! 
