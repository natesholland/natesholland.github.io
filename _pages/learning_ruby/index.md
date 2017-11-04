---
layout: page
title:  "Learning Ruby"
date:   2017-11-4 01:01:01 -0600
categories: jekyll update
permalink: "/learning_ruby/"
---

# Introduction to Ruby

These lessons assume that you are already a software developer and understand
the basics of programming but are looking to learn a new language.
If you are completely new to software development this guide will likely move a
little bit fast.

## Installing Ruby and Set Up

Most people in the Ruby world either use [rvm](https://rvm.io/) or
[rbenv](https://github.com/rbenv/rbenv) to install Ruby and manage the different
versions.
Take you pick and install Ruby.

In Ruby packages or libraries are called "gems" (like jars in Java or eggs in Python).
If you want to install a specific gem you can run the command `gem install gem_name`.
Bundler is the main package manager for Ruby (like pip in Python or Maven and Ivy in Java).
To install bundler go ahead and run:

```
$ gem install bundler
```

If you are working in an existing project or want to specify a number of dependencies
in your own project then you can use a Gemfile which is a file for specifying all
the gems your project uses.
The syntax for a Gemfile looks like this:

```ruby
source "https://rubygems.org" do
  gem "rails", "4.2.9"

  gem "faraday", "~> 0.10.1"
  gem "pg", ">= 0.18"
  gem "redis", "3.3.3"
end
```

Most of the version specifiers, like `>= 0.18`, are self-explanatory.
The specifier `~>` has a special meaning, best shown by example.
`~> 0.10.1` is identical to `>= 0.10.1` and `< 0.11`. `~> 0.10` is identical to `>= 0.10` and `< 1.0`.

This will get your environment set up.
To launch a Ruby console you can run the command `irb` or to run a ruby file you
can run `ruby my_file.rb`.

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
