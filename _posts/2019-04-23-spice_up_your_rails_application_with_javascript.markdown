---
layout: post
title:      "Spice up your Rails application with JavaScript"
date:       2019-04-23 16:20:19 -0400
permalink:  spice_up_your_rails_application_with_javascript
---

JavaScript is within the Top 5 programming languages to learn, mostly because of its flexibility. Any Rails application can benefit tremendously from using JavaScript, adding to the user experience. Today, I'll be walking you through how to add some flexibility into your existing Rails application using JavaScript and jQuery. 

### Set up your dependencies 
First things first, set up your existing rails app with the proper gems needed. In your gemfile, add in the ActiveModel Serializer gem, and either jQuery or rails_ujs. 

```
gem ‘jquery-rails’ 
gem ‘active_model_serializers’
```

Then, within your asset pipeline, in your application.js file, you'll need to require a few things to not run into any problems:

```
//= require jquery
//= require jquery_ujs 
//= require_tree
```

Those are the necessary files for my example, but here you can add others you'll need as well. Make sure you 'bundle install' before starting. Then, to make sure you're good to go, don't forget to add it into your views/layout pages so that they're properly rendered.

```<%= javascript_include_tag 'application', 'data-turbolinks-track': 'reload' %>```

### ActiveModel Serializer
There are many ways in which you can build an internal API for yourself, some trickier than others. Luckily, ActiveModel::Serializer has made it very easy for us. ```rails g serializer model``` creates a new file ```model_serializer.rb``` in a new folder, ```app/serializers```, within your app that sets up a serializer for you: 

```
class ModelSerializer < ActiveModel::Serializer
  attributes :id
end
```

Feel free to add in any other attributes you want to see parsed as json. Set up any relationships you have as well to be able to see them too. So, the json for a post that belongs_to an author would look like this: 

```
{
  id: 1,
  title: "A Blog Post By Stephen King",
  description: "This is a blog post by Stephen King. It will probably be a movie soon.",
  author: {
    id: 1,
    name: "Stephen King"
  }
}
```

### Set up your controllers
Within your controller for the model you created the serializer for, add in the ActiveModel::Serializer magic. 

```
def index
  @models = Model.all
  respond_to do |format|
    format.html
    format.json {render json: @models}
  end 
end
```

Congrats! You've set up an internal API for you to use, from here, I recommend starting by using ajax to render lists and items directly on the page without having to refresh the entire webpage. You now have an incredible user interface for your app!









