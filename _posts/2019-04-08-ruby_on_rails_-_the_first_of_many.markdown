---
layout: post
title:      "Ruby on Rails - The First of Many"
date:       2019-04-08 16:19:40 +0000
permalink:  ruby_on_rails_-_the_first_of_many
---



rails -g scaffold: one line of code to give you a fully-functional, working application. That right there is the true power of Rails. Obviously, I don't recommend anyone actually using scaffold, but it's crazy to think of the ability Ruby on Rails has. This project opened my eyes to how easy things can be using help from libraries and frameworks like Rails. For my project, I decided to do an application around something that I love, travel. Trailwaze is a travel application where you can share and browse different travel itineraries. Today, I'll be walking you through a high level of how to get your project off the ground based on my experience building Trailwaze. 

### Step 1: Choose an idea and set up Rails ###

This may seem like a very simple and obvious step, but actually it might be the most important. Beyond deciding what your project will be (Can't really give you advice on that, that's up to you, dear reader), it's really important you plan well before starting. Set your vision. Sketch your app out, either by hand or using Sketch, Adobe, Figma, whatever you prefer. Then, more importantly, plan out your models and relationships, and their respective fields. This step will save you any complications down the line. And finally, run rails new new-project on your command line. Make sure you have everything installed and check your latest versions of both ruby and rails to avoid any errors off the bat. Another important thing you should think about is where you will be hosting your application after, if at all. This will change what you use for your datebase. I ran into trouble trying to host on Heroku because sqlite3 is not supported, so I had to change to postgreSQL.

### Step 2: Generate your models and migrate db ###

This step should be very seamless, considering you have already mapped out your relationships and models in the previous step. rails g model ModelName fieldname:fieldtype --no-test-framework should get you going.  Generate your controllers for their respective classes and add in your relationships. Once you have all that setup, run rails db:migrate, and you'll be up and running! 

### Step 3: Time to Build ###

Now that you're pretty much setup, it's time to build. Personally, I like to build things in order of how I envision a user workflow to be. I'd start with signup, then login, then home page, etc. Get started with proper security here build your OAuth, secure passwords using the bcrypt gem, and authenticate your user with a callback in the controller. Make sure you set up your routes within config properly, use nested routes if necessary (modeling your relationships). While your building, make sure you don't overwork and do things that Rails or other libraries can help us iwth. I'm sure we're all victims of this consistently, but it's key to be efficient while building your application as well. Form helpers, layouts, and partials will save you a lot of time, for example. 

### Step 4: Deploy to Heroku ###

I found a few helpful articles online to help with this. Make sure you have set up your pg db correctly and it should be very simple. Basically, it's very similar to setting up your remote repo on GitHub. Here's a good link that could help you get started: [Learn.co Rails Heroku Deployment](https://learn.co/lessons/rails-heroku-deployment). 


Overall, this was actually a great-learning experience for me. Not because it was easy, but because it's the project where I've had the most bugs and challenges. One of the things that would have helped me the most was to plan better from the start. As I mentioned in Step 1, I had everything drawn out and modeled out, but over the course of my project I ended up doing almost a 180 on my plans. If I had taken more time to think about the feasability of my vision, I would've saved a lot of time and errors. Needless to say I'm happy I ran into mistakes and challenges. Eventually, I want to add a lot of features to this application and have a one stop shop for all your travel needs. Keep an eye out for any future updates!

