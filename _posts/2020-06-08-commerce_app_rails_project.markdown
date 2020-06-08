---
layout: post
title:      "Commerce App Rails Project"
date:       2020-06-08 15:26:52 +0000
permalink:  commerce_app_rails_project
---


### Overview

The assignment was to create a Ruby on Rails application with specific assiciations to demonstrate many of tools available in Rails. Other requirements like validations, error messages, omniauth sign in, filters, and nested routed and forms were also part of the test. I did this by creating a MVC structure that imitates how an online shopping system would actually work. I made database tables for products, merchants, and companies in order to create data my requests controller will pull from when a user generates a request.

Click [here](https://drive.google.com/file/d/1z8dQLtuFbSCwbLTNSknHRYKY25_7WIwx/view?usp=sharing) for user demo

Click [here](https://github.com/Biotruss/commerce_app_rails_project) for github repo

### Devise Gem

In my last project I made a Sinatra Application that used the MVC the generate and save the user session data so the user will stayed logged in when navigating between pages. So in this project I used the Devise gem to help set up that function this time. I placed `gem 'devise'` in Gemspec, ran `bundle install`, then ran` rails g devise:install` to install devise. Then I ran `rails g devise user` to generate user resources and `rails g devise:views` to generate view files for login, signup, ect. Next was to create the RegistrationsController and to permit all of the attributes you want for the user. Finally I needed to add the devise registration route to config/routes.rb: `devise_for :users, :controllers => {registrations: ‘registrations’ }`.

### Omniauth with Facebook
For this project I needed to implement omniauth signup and login so I chose facebook for this task. Devise also has functions programmed in it to allow the installation of the gems `omniauth` and
 `omniauth-facebook`. Inside config/initializers/devise.rb we tell our Rails app to use a piece of middleware created by OmniAuth for the Facebook authentication strategy. I used the gem `dotenv-rails` to hide my key and secret strings encrypted. Next was setup for sessions in the MVC directories. Finally was to got omniauth routes and params to devise in config/routes.rb.
 
 ### Setting up Requests
 I used rails to generate resources for requests and they would simple have in id, product_id, quantity, user_id, and merchant_id. The user chosses a product which is used to reference the merchant the posted the product. Merchants do no actually have funstion to create product in this app the relationships are just made to imitate this and data is created using seeds.rb.The only things the user enters is the product_id via a product dropdown menu and quantity. User_id and merchant_id are found and automatically saved as attributes to the object. MVC functions are added so user can index, show, create, edit, and delete request that they have made.
 
 ### Playing with nested forms and routes
 Part of the test for this project is creating a has_many through association. It is in this relaionship where I will have my nested user created objects. The requests objects can also have custom_requests nested to them through the form in the request new and edit routes. The custom_request objects have an attribute named description and this is suppose to simulation the situation where a user might have special delivery requests that the merchant might want to know. MVC functions are added to custom_requests so users can show, create, edit, and delete these objects. Nested routes are the made in config/routes.rb.
 
 ### Extras
 There were a few things I did at the end. Basic presence validations were added to the attributes within the models that users input data for. User input errors were added so that they will show as `placeholders` within the form itself. And a filter was added to the products index page so users can view product by merchant if they wish. I though about adding a filter to requests because that is a user created object, but I was attempting to impement it order by time created and that seemed like it would be a redundant way to apply this function to the program.
 
 ### Thoughts and Feelings
 On my coding journey with Flatiron I haven't  managed to grasp exactly how vast a tool Ruby on Rails is until I completed this project. I am starting to see this as a tool to manipulate and present data and tools to users that is only limited by the person programming the application. It all still feels daunting, but I am improving and learning things everyday!

