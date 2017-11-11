---
layout: page
date:   2017-11-11 01:01:01 -0600
categories: jekyll update
permalink: "/learning_ruby/metaprogramming"
---

## Metaprogramming

Ruby contains a large amount of metaprogramming which is somewhat unique to Ruby
and generally not available in other languages.
This allows developers to do a lot of really powerful (but often dangerous) things.
Some early Ruby developers get carried away with using metaprogramming to do fun
things that they were unable to do in languages they worked in perviously.
I would however caution against this and only use metaprogramming when absolutely
necessary.
It is very powerful but can be very difficult to maintain and understand
in the future.
So with that in mind let's look at some examples of metaprogramming.

One of the most common examples of metaprogramming in Ruby is the definition of
`method_missing` and `respond_to?`.
These methods together as a pair can let a Ruby developer define a lot of methods
"on the fly" without writing a whole lot of boiler plate code.
`method_missing` is the method that gets run when a Ruby class does not know how
to respond to a method call, and `respond_to?` is the method that tells what
an object responds to.
Here is an example of how we can make a currency exchange system using metaprogramming
and not a lot of code.

```ruby
class Currency
  CONVERSION_TABLE = {
    dollars: { dollars: 1, euros: 0.86, pounds: 0.76 },
    euros: { dollars: 1.17, euros: 1, pounds: 0.88 },
    pounds: {dollars: 1.32, euros: 1.13, pounds: 1}
  }
  attr_accessor :currency
  attr_accessor :amount

  def initialize(amount, currency)
    @amount = amount
    @currency = currency
  end

  def method_missing(method_name, *args, &block)
    # this is a conversion call
    if CONVERSION_TABLE.key?(method_name.to_s.gsub("to_", "").to_sym)
      destination_currency = method_name.to_s.gsub("to_", "").to_sym
      amount = (@amount * CONVERSION_TABLE[@currency][destination_currency]).round(2)
      currency = destination_currency
      Currency.new(amount, currency)
    else
      super
    end
  end

  def respond_to?(method_name, include_all=false)
    # this is a conversion call
    if CONVERSION_TABLE.key?(method_name.to_s.gsub("to_", "").to_sym)
      true
    else
      super
    end
  end

  def inspect
    "Currency: #{amount} #{currency}"
  end
end
```

So what this is doing is it's setting up a hash of conversions between a number
of different currencies and then dynamically making `to_dollars` and `to_euros`
and so on dynamically using method missing.

Here is how we could use this:

```ruby
> c = Currency.new(10, :dollars)
=> Currency: 10 dollars
> c.to_pounds
=> Currency: 7.6 pounds
> c.to_euros
=> Currency: 8.6 euros
> c.to_euros.to_pounds
=> Currency: 7.57 pounds
```

This is only one example of metaprogramming and Ruby on Rails libraries provide
a number of other powerful tools to use.
metaprogramming is really only limited by your creativity but I must warn you to
use it sparingly and think about the maintainability of your code when doing so.
