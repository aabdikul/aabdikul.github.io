---
layout: post
title:      "A Brief Visit to Core Object Oriented Ruby Concepts"
date:       2019-09-01 18:29:12 -0400
permalink:  a_brief_visit_to_core_object_oriented_ruby_concepts
---


We first learned Ruby from a Procedural standpoint: basic methods, hashes, and arrays. This was a great introduction into the next step: Object Oriented Ruby (OO). OO Ruby abstracts from procedural Ruby by interacting directly with the way that Ruby processes data types themselves; in other words, we are creating "classes" of data on which to program. These classes can include methods and variables with different scopes (i.e. class, local, and instance variables). With that said, I'll be walking through, with examples, the most common types of variables, methods, and their scopes. Let's begin with variables. 

A variable can be thought of as a placeholder for information within a program. It's the programming world's "blank" in a Mad Lib. There are a few types of different variables that exist within a class. 

**Local Variables** 

```
aida = "Aida" 
```

The above signifies a local variable - it can only be used in the runtime session of the block of code that your program is currently running. This presents limitations as it doesn't allow a user the flexibility of using this variable going forward. In other words, once the program is done running, "poof!" the variable is gone. 

**Instance Variables**

Instance variables solve for the limitations of local variables because they give a user the flexibility to use that variable in all methods within a class. Instance variables are instantiated with the symbol "@". This showcases its power when multiple methods use the same variable. If we look at the below snippet of code, we can illustrate this concept. 

```
class Person

attr_accessor: name 
@name = "Aida"

def hi 
puts "Hi #{@name}!" 
end

def bye
puts "Bye #{@name}!"
end

end

aida = Person.new
aida.hi 
aida.bye 
```

Looking at this very simplified code, one can see that I'm creating a new class, "Person". Within that person class, I have a setter and getter method (we will get into this later). Then, I have the simple methods, "hi" and "bye". In this code, "aida" becomes a new instance of the person class because I'm creating that instance by invoking the `.new` method. Once I've created this instance, I can then have this instance variable (aida) leverage the methods in that class `.bye` and `.hi`. When I use these methods, I'll receive the below result in my terminal: 

```
"Hi Aida!"
"Bye Aida!" 
```

**Attribute Accessors**

Before jumping to class variables, I want to touch on attribute accessor methods. These handy macros work to take the extra effort out of always creating setter (writer) and getter (reader) methods. A setter method "sets" an instance variable equal to a value. It also gives us the ability to make changes to the instance variable, should this be necessary. The below demonstrates a writer method: 

```
def name=(my_name)
@name = my_name
end
```

A reader method "reads" the instance variable. It is as follows: 

```
def name
@name
end
```

In tandem, these two methods are critical to creating instance variables in a class. Attribute accessor, as shown below, combines these two methods into one through a macro functionality. 

```
attr_accessor: name
```

A quick note: `attr_writer` and `attr_reader` methods are also available to use and function in similar ways to the accessor method. 

**Class Variables**

Unlike an instance variable, a class variable is instantiated by the symbol: "@@". It works on all instances of a class as opposed to an instance variable which only works on an instance of a class. A great example of a class variable in action is shown below:

```
class Person

@@people = []
attr_accessor: name

def initialize(name)
@name = name
@@people << name
end

end
```

In this simple code snippet, I'm demonstrating that I'm creating a new class, Person. Within this class, I have a class variable titled, "people". My desired functionality for this class variable is the aggregation of all instances created. In this case, each new "person" that is instantiated will get added via the shovel functionality into the class variable of "people". 

**Class Methods and Instance Methods**

Lastly, I'd like to touch on the differences between a class method and an instance method. An class method works on the entire class - that is its "scope". Looking at the below, leveraging our "Person" class, if I were to create a class method, it could look like this:

```
class Person

@@people = []
attr_accessor: name

def initialize(name)
@name = name
@@people << name
end

def self.all_people
@@people 
end

def hi(name)
puts "Hi #{name}!"
end

end
```

In this case, the `.all_people` method, because it's being invoked on the self keyword, which in this case means the class, will return all objects stored in the @@people class variable which was defined as an empty array. 

An instance method, on the other hand, is exemplified by our "hi" method. When invoked, this method will output "Hi Aida!" into the terminal because I'm giving the method the opportunity to interpolate whatever variable its given via the argument input. 

These are some of the many elements that must interact together in Object Oriented Ruby. They are all critical to the build of a successful OO Ruby program. 

