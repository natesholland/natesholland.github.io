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

### Set

### Open Struct
