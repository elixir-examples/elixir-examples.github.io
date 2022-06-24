---
layout: post
title:  "Split a string"
date:   2016-02-29 18:42:58 -0600
categories: string
---
This example shows how to split a string on whitespace or split on a string.

{% highlight elixir %}
["1", "2", "3"] = String.split("1,2,3" , ",")

# String.split/1 is useful to split on and strip whitespace
["1", "2"] = String.split("   1  \n \t   2 \n")

{% endhighlight %}


Documentation:

- [String.split/3](https://hexdocs.pm/elixir/String.html#split/3)
- [String.split/1](https://hexdocs.pm/elixir/String.html#split/1)
