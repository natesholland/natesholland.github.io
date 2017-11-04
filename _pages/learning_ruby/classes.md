---
layout: page
date:   2017-11-4 01:01:01 -0600
categories: jekyll update
permalink: "/learning_ruby/classes"
---

## Classes

Ruby is an object oriented language and everything in Ruby is an object, including
ints and strings!
Because of this understanding classes and how to define them is one of the core
building blocks of Ruby.
Let's look at an example and then talk about a few key points:

```ruby
class GatsbyCharacter
  BOOK_NAME = "The Great Gatsby"

  def initialize(name, age, description, hometown)
    @name = name
    @age = age
    @description = description
    @hometown = hometown
  end

  def name
    @name
  end

  def age
    @age
  end

  def introduction
    "Hello my name is #{name}! I'm #{@description} and I'm from #{@hometown}."
  end

  def self.book
    BOOK_NAME
  end
end
```

Let's break this down before we look at how to use it.
In Ruby the `GatsbyCharacter#initialize` method is a keyword for how you create new objects.
The `@variable` are "instance variables" and these are used to store state on the
object just like in java.
`BOOK_NAME` here is a constant which is the same for any instance of this class.
Then `GatsbyCharacter.book` is a class method which is called on the class and not
an instance.
Let's look at an example of how these methods get used.

```ruby
> nick = GatsbyCharacter.new("Nick Carraway", 29, "an unreliable narrator", "the Midwest")
=> #<GatsbyCharacter:0x007fab2403e540 @name="Nick Carraway", @age=29, @description="an unreliable narrator", @hometown="the Midwest">
> nick.name
=> "Nick Carraway"
> nick.age
=> 29
> nick.introduction
=> "Hello my name is Nick Carraway! I'm an unreliable narrator and I'm from the Midwest"
> GatsbyCharacter.book
=> "The Great Gatsby"
```

As you can see we initialize a new instance of the `GatsbyCharacter` class by calling
`GatsbyCharacter.new`.
This corresponds to calling the `initialize` method we defined earlier.
Note it is slightly odd that we define `initialize` but we call `new`: this is
a Ruby convention that you should get used to.
Finally note how the `GatsbyCharacter.book` method was called on the class and
not the instance `nick`.
This is because as we stated above that is a class method.
