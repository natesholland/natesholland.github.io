---
layout: page
date:   2017-11-4 01:01:01 -0600
categories: jekyll update
permalink: "/learning_ruby/loops"
---

## Enumerables and Loops

In Ruby there is a bit of a convention about using `each` to iterate over
iterables instead of using `for` as is more common in most languages.
Ruby does support the normal `for` loop flow but it is not common to find
in most Ruby projects.
The logic behind this is that it allows the underlying datatype to handle
how the iteration occurs without concerning the caller.
Here are some examples of how that works:

```ruby
array = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
array.each do |num|
  num * 2
end

hash = { foo: "bar", bar: "baz", baz: "bang" }
hash.each do |key, value|
  puts "#{key} maps to #{value}"
end
```

Here you can see that the exact implementation of how the elements are yielded
is left to the underlying data structure to handle.
This allows for interesting things like iterating over they keys and values in
a hash which would not normally be done with a for loop.

This also allows for a number of fun and helpful methods to be built on top
of this iterable pattern.
Some examples of this are the `map`, `select`, and `reject` methods.

```ruby
array = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
> array.map{ |e| e ** 2 }
=> [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
> array.select{ |e| e.even? }
=> [2, 4, 6, 8, 10]
> array.reject{ |e| e.even? }
=> [1, 3, 5, 7, 9]
```

Unlike `for` loops, `while` loops (or their equivalent) are used semi frequently in
Ruby applications.
Normally this pattern loops like a call to `while(true)` or the more simple and
syntactically pretty `loop`.

```ruby
loop do
  # do work
  break if condition
end

while true do
  # do work
  break if condition
end
```
