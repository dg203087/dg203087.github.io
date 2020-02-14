---
layout: post
title:      "Sinatra Marching Band Gig Sign Up Project"
date:       2020-02-14 17:52:01 +0000
permalink:  sinatra_marching_band_gig_sign_up_project
---


I am a member of the Lesbian & Gay Big Apple Corps (LGBAC), a community marching band in NYC. In fact, I’m the captain of the color guard. *holds for applause* We are a very active marching band with many gigs/parades, especially when the summer months are approaching. I was inspired to use this particular idea for my Sinatra project because of my frustrations with the process of signing up for gigs in my band. We need an easy way to sign up for gigs and edit and delete them as necessary.

Starting at the welcome page, the site gives a little history of the band and offers the user the chance to sign in or sign up to create their member profile. Once you are signed up/logged in as a member, you can view all your current gig sign ups on your profile page. The member can add a gig right from their page and view it immediately. This is done through the use of forms and the GET & POST routes. When a member is on their profile page, they can select any of their gigs to see that gig’s page with more information. If that gig belongs to the user, they have the ability to edit or delete it from the page. These routes, PATCH & DELETE, were a little more complicated to navigate, but the most useful parts of this site. On the current LGBAC website, a member can sign up for a gig, but there is no way to UN-sign up. So when the captains get an attendance list we have no way of knowing if a member has changed their RSVPS! Ugh!

Anyway. 

I thought the most challenging part of this project was building secure routes to each one of my pages. It was tricky to navigate all the possible options a member might want to take while visiting the website, and make sure they couldn’t do anything they're not supposed to. The helper methods in my application controller ‘logged_in?” and “current_member” make this easier. Each could be placed in my routes to assure the member was logged_in and associated with the correct gig before completing the action. 

Unlike with our CLI project, I was constantly finding new ways things could go wrong in my app! Is it normal to never feel finished in this profession? I have many thoughts on how I might add to this site. If I were to take this project one step further for use with our actual band I would:

* make the Add/Edit Gig features into drop downs so the members can only choose from a certain list of pre-populated events. 
* create “super members” who have the power to create/edit/delete gigs.
* create a way for all members to view gig attendance neatly on each gig’s show page. 
* recruit someone else to design it. <— Joke… or is it?  
