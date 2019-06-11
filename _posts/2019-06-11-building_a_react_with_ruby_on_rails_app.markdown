---
layout: post
title:      "Building a React with Ruby on Rails app"
date:       2019-06-11 13:39:23 -0400
permalink:  building_a_react_with_ruby_on_rails_app
---

A few things to note before we get started. React is a very powerful framework, so realistically, depending on the complexity of your app, firdst decide what back end would serve you the best. Ruby on Rails is a good middle ground when it comes to creating an API for your back end in terms of simplicity and complexity. However, if you are looking for an even simpler solution, I would recommend using [Firebase](https://firebase.google.com/docs/web/setup/) to build your API.

### Setting up your Ruby on Rails server
First things first, you need to set up your Rails backend. 
```rails new my-app --api```

The ```--api``` command simply tells your Rails app that you will not be needing any views within your app, and tha you will be using it just as an API. 

Run ```bundle``` to install your Gems. Create your models, set up your database, and seed some data; Then run ```rails db:migrate```

Now, it's time to set up some serializers so you can access your data as JSON data instead of the usual HTML you're used to. Add ```gem 'active_model_serializers'``` to your gemfile and run ```bunndle``` once again. Next, run ```rails g serializer Model``` to set up your serializer. You'll see within your app folder a new folder called /serializers. Set up the attributes you want to see in the API. 

```
class UserSerializer < ActiveModel::Serializer
  attributes :id, :name
  has_many :playlists
end
```

Set up your routes; I suggest namespacing them with Api to keep yourself organized. Create a folder called api in your controllers, and add in the controllers you'll need. 

```
class Api::UsersController < ApplicationController

  def index
	  @users = User.all
    render json: @users
  end
	
end
```

Now, if you start up your servers and go to http://localhost:3000/api/users, you should see a list of all your users. Now, you have a functional API you can use!

### Set up your React client

In terms of your folder structure, you can either keep your client within the Rails directories. I personally like to include it as a client folder within the Rails app, but you can also just keep a completely separate repo for it since they need to take two different hosts. 

Run ```create react-app``` wherever you want your React app to be. From here, I suggest changing your PORT to 3001, so that you can run your Rails server and your client side at the same time. Go into your page.json. You'll see the following: 

```
  "scripts": {
    "start": "PORT=3000 react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject"
  }
	```
	
	Simply change your PORT to 3001 or whatever you want, and you're ready to go. 
	
	Now, you're going to create your Components within React.
	
	```
import React, { Component } from 'react';
import './App.css';
import UsersContainer from './components/UsersContainer';

class App extends Component {
  render() {
    return (
      <div className="App">
        <header className="App-header">
        </header>
        <UsersContainer />
      </div>
    );
  }
}

export default App;
```

```
import React, { Component } from 'react';

class UsersContainer extends Component {
   state = {
	    users: []
   }

    render() {
        return (
            <div className="Users-container">
                Users
            </div>
        )
    }
}

export default UsersContainer;
```

Great! Now you have a very basic React app. Now let's connnect this with our Rails API in order to fill up our app with Users.

To simplify things, within our componentDidMount() of our Users Component, we will fetch the users from our backend and add them into our Users Component.

```
componentWillMount() {
   fetch("http:localhost:3000", {
	    headers: {
			   "Content-Type": "application/json"
		}
		   .then(response => response.json())
			 .then(data => this.setState({
			    users: data.users
		 })
}
```

Boom! Now you'll have access to users within your local state!

And with that, you have created a basic React app with a Rails back-end! I hope this was helpful, please leave any comments if you have any questinons, suggestions, or feedback.



