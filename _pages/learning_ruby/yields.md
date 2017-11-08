---
layout: page
date:   2017-11-4 01:01:01 -0600
categories: jekyll update
permalink: "/learning_ruby/yields"
---

## Blocks and Yields

As you may have seen in the iterables and loops section Ruby has something called
a block.
Blocks can be written with two different syntaxes.
If you are using a multi-line block then you should use the `do ... end` syntax
and if you are using a single line you should use the `{ ... }` syntax.
Here are examples of the same block written both ways:

```ruby
[1, 2, 3].each do |e|
  e ** 2
end

[1, 2, 3].each { |e| e ** 2 }
```

If you read any ruby you will see this pattern used in multiple ways.
Using predefined methods like this is pretty self explanatory and in my opinion
makes Ruby a pretty language to work with.

The underlying mechanic for these methods is the `yield` command in Ruby.
A call to `yield` returns control of the method to the block that is passed in
and then after the block is done control gets passed back to the calling method
after the yield.
This is a little bit difficult to explain in writing so here is an example.

```ruby
def method # optionally method(&block)
  puts "starting out"
  yield
  puts "wrapping up"
end

method do
  puts "inside the yield"
end
# results in
starting out
inside the yield
wrapping up
```

So you can see here we start by executing the beginning of `method`
then the `yield` executes the block that gets passed in and then control is returned
to the original method.

Additionally you can pass parameters into the yield which is what is happening
in the definition of the `each` method.
Here is a simpler example to demonstrate the concept.

```ruby
def new_method(&block)
  words = ["foo", "bar", "baz"]
  [0, 1, 2].each do |i|
    yield(words[i], i)
  end
end

new_method do |word, number|
  puts "Word: #{word} Number: #{number}"
end
# results in
Word: foo Number: 0
Word: bar Number: 1
Word: baz Number: 2
```
