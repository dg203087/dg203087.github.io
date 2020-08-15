---
layout: post
title:      "The Costume Exchange! Final React/Redux Project"
date:       2020-08-15 18:47:44 -0400
permalink:  the_costume_exchange_final_react_redux_project
---


For my final React/Redux project I chose to create an app that could be potentially very useful to me and many of my friends. We are all cosplayers based in NYC – always on the prowl for new costume ideas and pieces to add to our collection. As someone who has had to search for the “perfect emerald green Sailor Jupiter ankle boots” three days before New York Comic Con, I would love a place where I could search/borrow/purchase cosplay pieces with people in my area. Enter the NYC Costume Exchange. 

 The NYC Costume Exchange allows the user to:
* browse all available costumes
* post costume listings with a photo 
* delete a costume listing
* browse costumes by category

To start my project, I generated two resources – costumes and categories – with associations of a category has_many costumes, and a costume belongs_to a category. I seeded the database with a list of 6 pre-determined categories (i.e. “Film,” “TV,” etc.) to use in a dropdown in my front end. 

Then, to start in my front end, I set up the Redux ‘store’ in my index.js file. This is where Redux handles the state of the application in a centralized object that can be easily accessed by any component. Before moving on to the meat of the app, I also installed Thunk, which is middleware that allows me to send asynchronous requests to an external source by allowing the action creator to return a function rather than an object. I used Thunk in my 4 action creators - two fetch actions, to fetch costume and category info from my backend, as well as addCostume and deleteCostume actions. 

Index.js renders my App.js which contains 2 presentational components, a NavBar and footer, as well as my CostumesContainer component. My CostumesContainer is a class component which accesses props for both Costumes and Categories. This was necessary because I wanted to include a Category drop down in my costume form. My file structure is a bit wonky, but basically the CostumeContainer contains all my routes (using React-Router-Dom), however, my CategoriesContainer actually holds the Costumes component which renders all my costumes. This was to make easier to filter the costumes by category. This could probably be refactored (more like RE-organized!) in the future, but I did learn a lot through the process of organizing my components and routes. 

When I first started creating this project I was thinking my app would be the “AirBnb of Cosplay.” But I decided to take Z’s advice and build a bicycle before I built a motorcycle. Instead, I’ve aimed to build what Madeline had called a “Craigslist of Cosplay.” However, this app idea (and the encouragement of my Harry Potter group) has led me to want to build out this idea. Some next goals for this site include: 

FUTURE GOALS: 
* Adding a User model with a profiles photo
* Associating costumes particular user which would also appear on their profile.
* Creating the ability to “love” a listing and possibly add it to a list of likes of a particular user.
* Upload more than one photo and FIGURE OUT THE BAIN OF MY EXISTENCE ACTIVE STORAGE *bitterness*
* Adding additional functionality to search by location and/or size
* SUPER STRECH GOAL – Users friend each other and create their own costume exchange network.

