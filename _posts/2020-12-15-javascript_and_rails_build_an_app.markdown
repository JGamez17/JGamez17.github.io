---
layout: post
title:      "Javascript and Rails build an App "
date:       2020-12-15 06:31:57 +0000
permalink:  javascript_and_rails_build_an_app
---


For my 4th project in the Flat Iron software engineering program I have decided to create a NYC hiking trail app. Hiking is a hobby for me and often times I find myself wondering if I can find trails right in NYC. This app will allow users to view all trails by borough and leave comments on trails. The first step in creating this project was what I call "Phase I". Phase I is the planning phase of my app. During the planning phase I created a user story and identified the main parts of my app: The WHO, WHAT & HOW. Who- is my user, in the app the user will be able to view all trails by borough and see the name, location, length and difficulty of that trail. This app was made possible by using a Ruby on rails backend and a Javascript frontend. My final file structure contained two top-level folders that separated my backend from my frontend. 

I built my backend first by running the following code in the terminal: 

```ruby
rails new NYC_Hiking_api --API -G -M 
```

 Once this was created I ran rails g resource to create my models, controllers, relationships and migration. One of the challenging aspects of this project was creating an API from scratch. In order to successfully create an API I found the data I wanted to utilize and turned that into a giant array of objects.  Once all my files were setup I had to migrate my database. One major difference from using rails for my backend only is that now I am no longer using VIEWS to render any data to the web browser. Another major difference is in my controller, which now renders my variables with *render json*. My trails_controller looks like this:

```ruby
class TrailsController < ApplicationController
        before_action :set_trail, only: [:show, :update, :destroy]
      
        # GET /trails
        def index
          @borough = Borough.find_by_id(params[:borough_id])
          @trails = @borough.trails
          render json: @trails, except: [:created_at, :updated_at]
        end
```

If you notice now when rendering my data to the web browser at "[http://localhost:3000](http://localhost:3000/)" will show all my data in json format and will load all my attributes except when it was created and when it was updated, (pretty cool)! 

Welcome Javascript! Now utilizing javascript as my front-end it will render all my data to the web browser. Building my front-end was interesting and challenging. When I first started building out the application I felt extremely lost and confused, but with persistence and help from my cohort mates my dreams and vision for this app started to come true. My front-end consisted of object-oriented programming. Object oriented programming is the use of object to model real world things. In the case of my app, I have a TrailsComponent.js, BoroughButton.js and a comments.js. These three files consist of classes that represent in the digital world what they are in the real world.  They all consist of constructor methods that allow us to pass in arguments and initialize our objects. The constructor method utilizes the keyword **THIS** and refers to the instance that was created.  From building this application I gained a better and much deeper understanding of the beautiful language known as Javascript. I look forward to learning much more about javascript and mastering this language.
