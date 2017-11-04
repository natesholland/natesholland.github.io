---
layout: page
date:   2017-11-4 01:01:01 -0600
categories: jekyll update
permalink: "/learning_ruby/functions"
---

## Functions

As in almost any programming language functions are one of the key building blocks.
Here are the basics for how functions work in Ruby.
The first thing worth noting is that in Ruby the parenthesis are not required
unlike in many languages:

```ruby
def square(x)
  x ** 2
end

> square(4)
=> 16
> square 4
=> 16
```

### Passing Arguments

Additionally in ruby you can have named parameters.
In Ruby there are a few ways to defined defaults.
The old way in Ruby is to do the following:

```ruby
def foo(bar="default")
  bar + "!"
end

> foo
=> "default!"
> foo("baz")
=> "baz!"
```

But in Ruby 2.0 we introduced keyword arguments.
So the same things can be done with the following:

```ruby
def foo(bar: "default")
  bar + "!"
end

> foo
=> "default!"
> foo(bar: "baz")
=> "baz!"
```

You can also choose not to set a default which will require the argument
be presented.

```ruby
def foo(bar:)
  bar + "!"
end

> foo
ArgumentError: missing keyword: bar
```

One more cool thing Ruby can do is pass an unlimited number of arguments onto
a function like in the following example:

```ruby
def foo(bar, *more)
  bar + "! " + more.join(" ")
end

> foo("foo", "bar", "bang", "baz")
=> "foo! bar bang baz"
```

### Lambdas

Ruby also has Lambda functions which can be called as follows:

```ruby
plus_two_lamda = ->(x) { x + 2 }

> plus_two_lamda.call(4)
=> 6
```

These can be helpful and can even be passed in as an argument to another function.
