---
layout: page
date:   2017-11-4 01:01:01 -0600
categories: jekyll update
permalink: "/learning_ruby/install_and_setup"
---

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
