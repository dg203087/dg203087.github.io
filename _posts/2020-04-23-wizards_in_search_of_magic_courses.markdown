---
layout: post
title:      "Wizards in Search of Magic Courses"
date:       2020-04-23 21:20:31 -0400
permalink:  wizards_in_search_of_magic_courses
---


For the coding challenge during my Rails assessment, I was asked to add filtering functionality to the index page of my application. On the course index page, Wizards can view a full list of the courses available during my upcoming Wizard Retreat Weekend. The course list could eventually become long and having search functionality could come in handy. 

After giving it a moment of thought, I knew that I would need to:
1. Add some sort of form to my index view
2. Use an Active Record scope method in my Course model to filter by NAME
3. Call the action in my controller

This is where the googling began. 

**MODEL **

All the documentation suggested I start with creating a search method in my model first even though it was my instinct to start with the view. 

My `.search` method would be a class method because it is called on the Course. The method accepts one variable `search_name`, that is, whatever the user types into the search, and then immediately verifies the variable’s existence. If nothing is typed the search bar all instances of Course will still appear – which is established in an if statement. 

```
def self.search(search_name)
        if search_name
            *# this is where I search for matches*
        else
            @courses = Course.all
        end
end
```

Now that I had my if statement set up, there were multiple ways I could search for matching instances of Course. I had to decide what kind of functionality I wanted my page to have. I could search for EXACT matches by using the Course.find_by. The find_by method will review all instances Course and return the one(s) with the name attribute that match exactly.  

```
this_course = Course.find_by(name: search_name)
            if this_course
                self.where(id: this_course)
```

However, I wanted by page to have additional functionality to search for close or LIKE version of the search item typed in. People do not always type using capital letters or there may be two objects with similar names. So, I used a bit more SQL to call all instances of Course with a name LIKE the one that was typed. The % before and after the interpolation can represent zero, one, or multiple characters – and will return any instance of Course that include the characters typed in the search. 

So the full method is: 

```
def self.search(search_name)
        if search_name
            self.where(" name LIKE ?", "%#{search_name}%")
        else
            @courses = Course.all
        end 
end
```

**CONTROLLER**
 
I called the .search method in my Courses Controller index action, passing in whatever the user types into the search box, and set it equal to the instance variable @courses to be called upon in the view. This order of operations makes sense. 

```
  def index
    @courses = Course.search(params[:search])
  end
```

In addition, I had to make sure I added :search to my course_params (strong_params) method so that the search parameter is permitted. 

**VIEW**

Finally, I added a form to my view. 

```
<%= form_tag courses_path, :method => "get" do %>
    <%= label_tag(:search, "Find Course: ") %>
    <%= text_field_tag :search, params[:search] %>
    <%= submit_tag("Search", :name => nil) %>
<% end %>
```

A few key elements I learned while accomplishing this: 
1.	Use a GET request. Nothing is persisted to the database so a POST method is not needed. 
2.	The form is submitted to the `courses_path` – same page! We’re not going anywhere. Took me second to think about but makes total sense. 

Fun. Below are a few places on the interwebs that were particularly helpful. 
* This Flatiron grad Megan had a similar problems and explained it thoroughly: [](https://dev.to/mwong068/adding-a-basic-search-form-in-rails-5hnl)
* This developer Melvin who goes deep about using SQL for searches: [](https://melvinchng.github.io/rails/SearchFeature.html#chapter-4-search-feature)




