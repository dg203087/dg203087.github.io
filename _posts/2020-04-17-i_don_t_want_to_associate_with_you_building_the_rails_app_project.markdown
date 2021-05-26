---
layout: post
title:      " I don’t want to ASSOCIATE with you: Building the Rails App Project"
date:       2020-04-17 23:16:40 -0400
permalink:  i_don_t_want_to_associate_with_you_building_the_rails_app_project
---


If Rails is magic, then I’m a muggle who’s just arrived in Diagon Alley. Every time I think I understand associations I learn something else they can do. 

My Rails app is a user registration system for my upcoming Wizard Retreat Weekend. I organize the NYC Harry Potter Meetup (The Group That Shall Not Be Named) and we are planning weekend retreat for our members. Wizards who sign up for the retreat on the app can register for courses as well as edit or cancel their registrations. I want each wizard to be able to join multiple courses and make the most of their weekend, but I also want courses to have many wizards because that’s where the fun begins (Quidditch, anyone?)! 

So, I can’t use a regular has_many/belongs_to relationship between the Wizard and Course classes. Doing so would allow me to associate many Courses with a Wizard, but not vice versa. This is where the has_many, through: association comes in. This association sets up a join table (Registration) which allows a Wizard to register for many courses, and a course to have many Wizards through Registrations. It’s a many-to-many relationship. 

I drew this work of art when starting my project to understand the type of data associations I was setting up. 

<a href="https://ibb.co/PwB1Q3m"><img src="https://i.ibb.co/XSmF8N2/IMG-3108.jpg" alt="IMG-3108" border="0" /></a>

I’m not quitting class to become an artist or anything. 

I learned that Associations gives the user access to several helpful Active Record query methods. I didn’t fully understand all the uses of these query methods when I started designing my project but discovered many ways they could be put to good use while coding.  I used the WHERE method in my Wizard model. The WHERE method allows the user to specify the parameters that a dataset should meet. As in, I created a method called Gryffindor, that allowed me to select only those Wizards in the database who share MY house. I then called this method in my controller and printed the list in my views with emails. Now, the Gryffindors can all connect before the retreat and soak up each other’s awesomeness.  

