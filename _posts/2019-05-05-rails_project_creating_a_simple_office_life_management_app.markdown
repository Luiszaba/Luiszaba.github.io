---
layout: post
title:      "Rails Project: Creating a simple office / life management app"
date:       2019-05-06 02:18:38 +0000
permalink:  rails_project_creating_a_simple_office_life_management_app
---


As we arrive near the conclusion of the Ruby on Rails lessons plan we are given the task of creating an application of our choosing that demonstrates our understanding of the Rails framework.  Coming from a corporate background I am too familiar with the consequences of mismanagement in the office.  So I decided to attempt to create a simple office management app using Rails.  However, this was not my first choice.  My first attempt was to create a Twitter clone.  This would have used ActiveStorage allow the user to host photos of their choosing.  As I was building the app, I realized there was not much use for this web page outside of hosting photos, something that many websites already do, and do a much better job at.  Does this mean the site created for my Rails project is better than many other websites that do the same thing?  The short answer is, no.  This does however provide a decent proof of concept should I ever want to build upon this in the future.  

With this app I decided to use Devise for the authentication, alongside OmniAuth for Facebook.  The Devise gem offers a variety of authentication methods and protections without the need to write much code.  The gem must be added to the gemfile and then installed into the framework using the following commands:

1. Add Devise to gemlist -> gem 'devise'

2. Via terminal -> $ bundle install

3. Via terminal -> $ rails generate devise:install

4. Enter './config/environments/development.rb' and add the following line: config.action_mailer.default_url_options = { host: 'localhost', port: 3000 }

5. Via terminal -> $ rails generate devise MODEL
Replace MODEL with the name of the model which will be used to hold your user/admin configuration

With those steps taken you have successfully installed Devise into your application.  With Devise you are able to use controller helpers that you otherwise would have needed to write yourself.  Note to whomever is reading this and would like to use Devise in the future, Devise will not handle all user authorization.  It is still necessary to write the code in your controllers to prevent any unwanted adjustments to your database, or exposing confidential information.  Devise is also Omniauthable, which means it will work with an OmniAuth of your choosing, given you follow the documentation for the website you are using.  

The app I created allows a user to create a specific task, assign the task to a user with a duedate, and have the user signal if it was completed or not.  The user can also be assigned to a group which handles a specific type of task, for example: Group(s) "Pets", "Household", "Office Supplies", "Javascript", ect.  


