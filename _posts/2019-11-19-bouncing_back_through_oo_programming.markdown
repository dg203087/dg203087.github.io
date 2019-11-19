---
layout: post
title:      "Bouncing Back through OO Programming"
date:       2019-11-19 15:35:10 -0500
permalink:  bouncing_back_through_oo_programming
---


In the week following Halloween, I felt a little behind. Object Orientated Ruby was putting me through it and I felt like everything I had learned in the weeks prior wasn’t sticking. I specifically was challenged by RELATIONSHIPS between classes and how they can interact across multiple files. I understood conceptually how a class could HAVE MANY of or BELONG TO another class, but how to accomplish this seemed vague and variable. 

The key to understanding relationships, I’ve learned, is learning how to pass around objects. Objects in Ruby are a metaphor for real life in that an object in code reflects a real-life object. A dog is a real-life (living and breathing!) object with behaviors and attributes. Behaviors like when someone rings the doorbell the dog barks (EVERY TIME if you’re my dog) or getting excited when they go on a walk. All dogs have attributes like their name, breed, and color. 

Objects in code reflect the real-life objects they represent. If Dog is an object in my code, it could be assigned attributes like: 

```
class Dog

attr_accessors :name, :breed, :color

def initialize(name)
     @name = name
end
```

Once the name has been set, I can ask the dog object about its name by calling Dog.name.  I can also invoke a behavior of the object like creating a method walk which changes the dog’s mood to “happy.”  

```
def walk
     mood = "happy"
     puts “#{name} is going for a walk and is now happy.”
end
```

As I move forward in the program, coding becomes more inspired by real-life every day. Now if I could only get my code to walk my actual dog. 

