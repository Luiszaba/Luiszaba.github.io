---
layout: post
title:      "Sinatra Project"
date:       2019-03-25 21:10:52 +0000
permalink:  sinatra_project
---


The Sinatra project has come and gone and I learned some things that I found interesting.  I am humbled by how much I've learned since joining the Flatiron School.  Moving on from the CLI Project, we are now starting to just break the surface of web development.  With all honesty, it's a humbling experience.  

Starting off our introduction to Sinatra, we are reintroduced to MVC (model, view, controller) file structure.  We have a (M)odel that inherits information and associates information from our database, the view will represent our user interface so our users can manipulate his/her information, and a controller to work in the background directing our user and data to where it needs to be.  Followed by HTML and Sinatra forms, validating user information, creating a session (cookies) to persist information across the website, and  RESTful routes which simplified how we view urls, and simplify our routes. 

For my first Sinatra project, I decided to create a simple website for fans of horror stories.  The user will sign in, create a horror story, and share it with others who have an interest in horror stories. They can then update, their story should they need to make any edits.

First thing I needed to do is make sure every user that creates an account and logs in is in a secure session.  For this I used:  

`enable :sessions set :session_secret, SecureRandom.hex(64)`

I also needed to ensure the user's data will not be hijacked so I set up a nice little helper method to check the user[:id]

`helpers do        
   def logged_in?
   !!session[:user_id]
end`

We need to create two models to associate with our database.  
Since I now have a secure password, and session for my user I went on to build the database.  The database has a Users table, and a Stories table.  A user model has many stories, and our story model belongs to a user. Our website will validate the users credentials and secure.  This is held in the User model

`has_many :stories
  has_secure_password
  validates_presence_of :username, :email, :password`
	
	Our views are placed three folders, Registrations: create users , Session - login & out,  Stories - views our forms and user created information, and Users - view stories the user created.
	
	Although my code is messy and not very elegant, it's still something I did and I have to say, I'm proud of myself.   The only thing to do next is to add pretty css to liven up the website.  Maybe a halloween theme, perhaps?  Only thing I wanted to do was add a little up-down voting system, but because of lack of time due to recent events, I just haven't been able to fit it in.  I was also held back due to my own failure to listen to warnings about opening .bash files in Windows Explorer.  
