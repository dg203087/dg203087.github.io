---
layout: post
title:      "Higher, Futher, Faster - Superhero CLI Gem Project"
date:       2019-12-06 21:49:28 +0000
permalink:  higher_futher_faster_-_superhero_cli_gem_project
---


For our first project, we were required to create a Ruby gem that interacted with a user in the CLI. We were asked to use scraping or an API to obtain data and use object orientation to store the information in instances of objects. 
I knew I was going to use an API from the start, as it was highly advised that we do so, and I didn't want to chance that my program might break at the last minute! I considered multiple APIs before settling on the Superhero API. I could see the real-world applications of this API. Being a cosplayer myself, I can't tell you how many times I've needed to look up a character based on their powers, features, or relationships to other characters. This project would be the starting point to something I've wished existed for years!

The Superhero API was free and open, requiring only to connect to my Facebook account before providing me with an access token. The user could call on the info from the API by ID, name, appearance, etc. There were so many features to choose from, I had to select a handful I knew would be most meaningful for my project. I didn't encounter any issues while connecting to my API, however, because there were 731 superheroes and all calls needed to use a specific ID or name, I was forced to hard code certain items that would otherwise have been more customizable. 
The gem I created allows the user to first browse a list of popular superheroes and select one they would like to know more information about. It also allows the user to search by letter and returns a list of superheroes whose name begins with that letter. From there, the user can select a hero or villain from the list to learn more about.  Initially, my program only had the ability to print the popular superheroes list and return information, however, I really wanted to challenge myself to see if I could create a search by letter method. I knew this could be eternally useful in real-life search scenarios. 

In this gem, object orientation is applied through 3 classes: Superhero CLI, API, and Hero. The CLI class dictates the structure of the gem. It allows the user to interact with the gem using text commands, like "menu," "list," "alpha" or "exit." The API class pulls the data in the form of a hash from an external source and organizes it before calling a new instance of Hero. That's where the Hero class comes in to initialize all hero objects that have been called. If multiple instances of the Hero class are created, like, say, in an alphabetized list, they are stored in the .all class variable. The info stored in the Hero class is then accessed by the CLI class and formatted to print for the user. 
WHEW. So much action for such a simple program!
In the end, I am proud of myself for working through the "I AM A GENIUS WHO IS SO GOOD AT CODING" moments as well as the "I AM THE WORST EVER, WHY AM I DOING THIS? LEAVE ME HEAR TO DIE" moments. It was a challenging experience, but I learned so much in the process. I feel ready to move on to the next adventure - Higher, Futher, Faster baby! 
