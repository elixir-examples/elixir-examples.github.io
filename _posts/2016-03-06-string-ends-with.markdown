---
layout: post
title:  "Test if a string ends with another string"
date:   2016-03-06 12:50:58 -0600
categories: string
---
This example shows how to check if a string ends with a given suffix.

{% highlight elixir %}
true = String.ends_with?("Period.", ".")

# True if any of list values match:
true  = String.ends_with?("Period.", [".","?"])
false = String.ends_with?("      !", [".","?"])
{% endhighlight %}

Documentation: [String.ends_with?/2](http://elixir-lang.org/docs/stable/elixir/String.html#ends_with?/2)
