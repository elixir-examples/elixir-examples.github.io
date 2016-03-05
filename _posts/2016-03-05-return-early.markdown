---
layout: post
title:  "Return early"
date:   2016-03-05 13:30:58 -0600
categories: kernel
---
There is no `return` keyword so code must be organized to return early. The follow example shows how to organize code to return early in Elixir.

For example, the early return in ruby:
{% highlight ruby %}
def hello
  if some_condition
     return "Goodbye"
  end
  do_this()
  do_something()
end
{% endhighlight %}

Could look like this in Elixir:
{% highlight elixir %}
def hello do
  if some_condition do
    "Goodbye"
  else
     do_this()
     do_something()
  end
end
{% endhighlight %}


Case and cond can also be used to return different values based on a condition.

See Also:

- [Case Statement](/examples/case-statement)
- [Cond Statement](/examples/cond-statement)
