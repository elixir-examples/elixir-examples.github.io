---
layout: post
title:  "Tuple syntax"
date:   2016-03-03 03:50:58 -0600
categories: tuple
---
This example shows the literal syntax to create a tuple and also how to pattern match.

{% highlight elixir %}
{:ok, 1, "a"}

# pattern match
{:ok, result} = {:ok, "good"}

# this raises a match error
{:ok, result} = {:ok, "good", "one more"}

# empty tuple
{}
{% endhighlight %}
