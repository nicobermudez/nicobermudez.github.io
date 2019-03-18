---
layout: post
title:      "Sinatra Project - "The Click""
date:       2019-03-18 11:12:47 -0400
permalink:  sinatra_project_-_the_click
---


It's been one month since my last project, the CLI Project. I think Sinatra was a big step towards my learning. It's the first time creating something *real*, something people can actually use, and would use. The first time the world of code suddenly 'clicked' in my head. Obviously, Sinatra is miniscule compared to Rails, but still, I created an actual application. I created an application called GOAL, where users can create goals and share them with other users. I wanted to keep the idea simple, with my main purpose to learn how to actually build the application, but also relevant enough where it might seem cool and useful in the future. Let's walk through how I built this application.

### Step 1: Organize your file structure ### 
![](https://i.imgur.com/toNkNxR.jpg)

It's very important you start by organizing correctly and updating your Gemfile to reflect the gems you'll need. Once you have that all set up. It's time to start building your application! 

### Step 2: Set up your Database and Models with ActiveRecord ### 

Once you have your models set up and relationships set, don't forget to use ActiveRecord. For your models, you'll simply set it as: class User < ActiveRecord::Base. While for your tables you'll use the Migrate command of ActiveRecord. Here's an example of a migration: 


class CreateProducts < ActiveRecord::Migration[5.0]
  def change
    create_table :products do |t|
      t.string :name
      t.text :description
 
      t.timestamps
    end
  end
end

Then, I'll you have left to do is migrate the actual database using rake db:migrate. Feel free to use a seed folder to add some preliminary data before starting.

### Step 3: Views and Controllers ### 

Now for the fun part. Here's where you're actually building the application the user is interacting with. Your views will reflect the user experience and talk to the controller to define the proper CRUD state for each view / form. Within your view you can also use '<style></style>' to add some CSS to your HTML file and '<script></script>' for some JavaScript... Just to keep things a bit exciting. Create a controller for each of your models. Don't forget to authenticate passwords and validate user inputs within your models as well! I found the Ruby bcrypt gem to be very helpful for proper security. Lastly, I used Flash to generate error messages for users to know when they did something they weren't allowed to do or when they scuessfully performed an action. 

### Step 4: Deploy app on Heroku ###

Finally, make sure you do something with your app! Don't just do all of that work and not reflect on wat you've learned. Write a blog post, record a walk-through, deploy the app on Heorku and gather feedback! Obviously, this is all very early stages for me, so the important part is that I learn from doing, and learn from feedback. Overall, this has been my favorite part of the program so far, I'm excited to continue building apps I can launch in the real-world.


