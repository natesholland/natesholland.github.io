---
layout: page
date:   2017-11-4 01:01:01 -0600
categories: jekyll update
permalink: "/learning_ruby/data_types"
---

## Basic Data Types

In Ruby most projects can be built using a few main datatypes.

### Hash

One of the most commonly used objects in Ruby is the hash.
This is the same as a dictionary in Python or a hashmap in Java.
In Ruby they keys and values of a hash can be any kind of object which can
lead to some interesting code but most often the keys are strings or symbols.
Ruby has a number of different syntactical ways to use hashes.
Here are some examples.

```ruby
{:foo => "bar"} == {foo: "bar"} # true, these are equivalent

> hash = {"foo" => "bar"}
> hash[:foo] = "bang"
> hash # notice the difference between the string "foo" and symbol :foo
=> {"foo"=>"bar", :foo=>"bang"}

> hash.each { |k, v| puts "Key: #{k} Value #{v}" }
Key: foo Value bar
Key: foo Value bang

hash[:foo] # "bang"
hash["foo"] # "bar"

> hash.values
=> ["bar", "bang"]
> hash.keys
=> ["foo", :foo]
```
For more documentation on the Hash class click [here](https://ruby-doc.org/core-2.4.0/Hash.html).

### Array

Arrays are one of the most common datatypes alongside hashed in Ruby.
There isn't very much special about Arrays in Ruby other than that they can
contain any object and are not required to contain a certain kind of object like
in Java.
Here are some examples.

```ruby
> array = [1, "two", 3.0]
=> [1, "two", 3.0]
> array << :four # this is known as the "shovel operator"
=> [1, "two", 3.0, :four]

> array[0] # 1
> array.include? "two" # true

array.each do |element| # iterating over the elements
  puts element
end
1
two
3.0
four
```

For more documentation on the Array class click [here](https://ruby-doc.org/core-2.4.0/Array.html).

### Strings and Symbols

Since everything is an object in Ruby, every String has a different object ID and a different location in memory.
Therefore Ruby also has symbols which are like strings but they are immutable and
only have one instance in memory.
In ruby you can also use #{} to do string interpolation.

```ruby
> symbol = :foo
> string = "foo"
> string == symbol # false
> "3 squared is #{3**2}"
=> "3 squared is 9"
```

Here is an example of multiple instances of the "same" string will have different
`object_ids` but multiple instances of the "same" symbol will all map to the same
object.

```ruby
> symbol = :foo
> string = "foo"
> another_symbol = :foo
> another_string = "foo"

> symbol.object_id
=> 1167388
> another_symbol.object_id
=> 1167388
> symbol.object_id == another_symbol.object_id # true

> string.object_id
=> 70238923074400
> another_string.object_id
=> 70238922898740
> string.object_id == another_string.object_id # false
 ```

 For more documentation on Strings click [here](https://ruby-doc.org/core-2.4.0/String.html)
 and for more on symbols click [here](https://ruby-doc.org/core-2.4.2/Symbol.html).

### Set

In Ruby sets are used a little bit less frequently than the other main datatypes
but they can still be very useful.

```ruby
require 'set'
> set = Set.new
=> #<Set: {}>
> set << "foo" # you can use the shovel operator here as well
> set.include? "foo" # true
> set << "bar"
> set.to_a # convert the set to an array
=> ["foo", "bar"]
> set.each { |element| puts element } # iterating over a set
foo
bar
```

For more documentation on the Set class click [here](http://ruby-doc.org/stdlib-2.4.2/libdoc/set/rdoc/Set.html).

### OpenStruct

OpenStructs are a lesser known datatype in Ruby that I am a fan of.
They are basically wrappers around hashes (and can even be initialized with one).
However, they provide a slightly prettier interface and in my opinion can be
very useful for passing back multiple results from a method.

```ruby
require 'ostruct'
> fruit = OpenStruct.new
> fruit.color = "red"
> fruit.name = "apple"
> fruit.grams = 100
> fruit.name
=> "apple"

# note that you can also initialize OpenStructs with hashes and compare them
> fruit == OpenStruct.new({name: "apple", color: "red", grams: 100})
=> true
```

If you want to delete a method off of an open struct you need to use `delete_field`.

```ruby
fruit.delete_field(:grams)
> fruit.grams
=> nil
```

For more documentation on the OpenStruct class click [here](https://ruby-doc.org/stdlib-2.0.0/libdoc/ostruct/rdoc/OpenStruct.html).
