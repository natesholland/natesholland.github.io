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

### Strings and Symbols

### Set

### Open Struct
