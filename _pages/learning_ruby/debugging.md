---
layout: page
date:   2017-11-14 01:01:01 -0600
categories: jekyll update
permalink: "/learning_ruby/debugging"
---

## Debugging

One of the challenges developers often run into when learning a new language is
figuring out how to debug their problems.
One of the most common ways to debug is to use a REPL (Read-Eval-Print-Loop) tool.
A common tool for this is the pry gem.
To debug a user puts a call to a debugger tool like pry in the middle of their
code and then they can poke around in the code.
One helpful rubyism is that you can call `method(:method_name).source_location`
and Ruby will show you exactly where that method is defined.

```ruby
def some_method
  binding.pry
  troublesome_method_call
end

> troublesome_method_call
 => StandardError
> method(:troublesome_method_call).source_location
 => "/user/code/app/models/something.rb#27"
```
