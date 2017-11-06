---
layout: page
date:   2017-11-4 01:01:01 -0600
categories: jekyll update
permalink: "/learning_ruby/control_flow"
---

## If Else Case and Control Flow

Ruby's supports all of the standard control flow elements.

```ruby
if condition
  # do work
elsif condition
  # do work
else
  # do work
end

case variable
when "A"
  # option A
when "B"
  # option B
when "C"
  # option C
else
  # the else condition
end
```

There are also a few cool little syntactic things that Ruby provides:
the `unless` command and the postfix if.

```ruby
do_work if some_condition_is_met
# is equivalent to:
if some_condition_is_met
  do_work
end

unless condition
  # do work
end
# is equivalent to:
if !condition
  # do work
end
```
