---
layout: post
title:      "From Sinatra to Rails"
date:       2020-05-18 04:30:24 +0000
permalink:  from_sinatra_to_rails
---

I found the journey from Sinatra to Rails to be both interesting and frustrating at times. I also now completely understand why Rails is viewed almost as if it is its own language separate from Ruby. In a lot of ways, Rails goes out of its way to simplify code for developers. Where Sinatra at times felt clunky, Rails makes things easy and time-efficient. However, I am glad to have learned Sinatra before jumping to Rails. 

For me, jumping to leveraging `form_for` was a pleasant surprise simply because it cut down the amount of time required to create a form. Instead of typing out each field required for the HTML on an `.erb` page, Rails gives you a quick and nifty way of using a FormBuilder that also interacts with the database. Similarly, using partials with forms cut down on just the sheer look of the code inside of the views - gone are the lenghty, nearly identical, forms - replaced with partials that pull from a single view. 

Another think I absolutely loved about Rails were the generators. Instead of manually creating migrations, a simple bit of code: `rails g resource User name:string --no-test-framework` could net you a migration, a controller, and a folder for future views. 

Additionally, I enjoyed learning how to manipulate my user's journeys by giving them access to nested hashes. Not every page needed to be created but instead, through the power of nested resources, I could associate different aspects of my application "automagically" and leverage the same CRUD actions in my controllers. I no longer need to build individual actions, I just need to build sophisticated logic in my controller to take care of this. 

Lastly, I've seen Oauth in so many places and have never truly experienced its power from a developer standpoint. Using another strategy's Oauth capabilities lets you off the hook in terms of storing passwords and usernames in my own database. That opens itself up to all kinds of risks and Oauth effectively eliminates that risk and gives the application a sophisticated feel. 

On the frustrated side, I definitely had a hard time adjusting at first to the idea that Rails took care of so much for me. I didn't need to write the actions and routes inside of the controller, that was all taken care of in my routes file. Adjusting to this definitely took time. Secondarily, I felt like I really needed to get the hang of how the `form_for` corresponded to the actual HTML that it spit out. Understanding this was critical because the `params` hash is still very much a functional part of Rails. 

For my project, I decided to create a "fencing club" where students can interact with coaches by taking lessons. They can schedule lessons and cancel them. They can search for certain coaches and sign up for lessons with those coaches by leveraging nested routes. I enjoyed working on this project and feel that I can continue to flesh it out to its full potential!
