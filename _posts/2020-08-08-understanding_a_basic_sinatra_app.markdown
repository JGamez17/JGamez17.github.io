---
layout: post
title:      "Understanding a basic Sinatra App "
date:       2020-08-08 05:39:40 +0000
permalink:  understanding_a_basic_sinatra_app
---


For my second project at Flat Iron school I built a content management web app using the Sinatra framework. What is Sinatra ? Sinatra simply put is for building web applications in a short amount of time.  Sinatra is able to communicate with a web server using a series of HTTP (hypertext transfer protocol) requests.  The two most commons HTTP methods are GET & POST. The GET method is used to request data from a specific source. POST methods are used to send data to a server to create/update a resource.  These requests are written inside of a controller which is part of an architectural pattern known as MVC (Models-Views-Controllers). MVC provides a separation of concern for our web app. 

The essential components of a Sinatra Application are config.ru, environment.rb, and Rakefile. 

### config.ru

The [config.ru](http://config.ru) file is what gets your app started (executable file). To start your application you type rackup [config.ru](http://configu.ru) into your terminal and in your web browser go to [localhost:9292](http://localhost:9292) and see your web app. 


```
require './config/environment'

if ActiveRecord::Migrator.needs_migration?
  raise 'Migrations are pending. Run `rake db:migrate` to resolve the issue.'
end

use Rack::MethodOverride
use SneakerController
use UserController
run ApplicationController #always last line
```
> *Above is an example of what a [config.ru](http://configu.ru) file would generally look like. This file allows your applications components the ability to communicate with one another*

The first line of code in this file is require './config/environment' and it is requiring the data present inside of the environment.rb file. Further down on lines 7-10 these are our mounted controllers, that allows our app to know about specific controllers.

### config/environment.rb

Then there is your environment file which allows your application the ability to communicate with one another. 

### Rakefile

The rakefile is a task manager and allows you to perform specific tasks and describe dependencies.

### app Folder

This folder is the core of our Sinatra project and contains the models, views, and controllers folders.

In Sinatra models are written as a ruby class, views are written in .erb files and the controllers file contain all of our logic.  Then their is the app controller which handles all incoming requests from the app.  Inside this very controller you'll see that it inherits from Sinatra::Base, which is a Ruby class that provides the evaluation of a Sinatra app.

After you have created all the above files you can start building your routes. To start my project I

used a Ruby gem called Corneal. It was created by a former Flat Iron student and it allows you to generate a full Sinatra Application.  To get started you simply type gem install corneal and you'll get folders/directories and create the necessary folders after. 

Finally, running SHOTGUN in your terminal lets you see what is going on in real time and see what your code would look like for your users. This part is very magically and rewarding at the same time.
