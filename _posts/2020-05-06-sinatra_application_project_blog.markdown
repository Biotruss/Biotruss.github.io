---
layout: post
title:      "Sinatra Application Project Blog"
date:       2020-05-07 03:57:00 +0000
permalink:  sinatra_application_project_blog
---

### The Project

My project is a simple sinatra-active_record application that imitates how an actual blog would function. In this blog application users are encouraged to write about their favorite games! Users need to signup and must be logged in to use the application. Users will be able to read posts created by other users and create posts of their own. Another function is that an individual user can only edit and delete posts that they have created themselves. When users are done they can logout and return to create new posts and edit old ones as they please.

Click [here](https://drive.google.com/file/d/1LXP371UtrfaitAR23IU1vsJj0jUygSHM/view?usp=sharing) for user demo
Click [here](https://github.com/Biotruss/sinatra_application_project) for github repo

### User Authentication

The first thing I needed to do was set up user authentication. This required storing user data and remembering to encrypt sensitive data like their passwords. This is necessary in order to remember users and later connecting those users to the posts that they have written. Having created a database for users allows me to remember them for when they want to log back in. A model was also created to establish their attributes and their relationship with posts.

### User Posts

A posts database was then needed and their belongs_to relationship with their user is maintained with a user_id attribute. Posts needed a controller that would contain routes to allow users to create, read, update, and delete posts. When a user creates a posts their unique user_id is stored inside the post object. We then test to see if the user and post objects share the same user_id if the user wishes to update or delete a post.
