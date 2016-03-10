---
layout: post
title:  "Pin operator"
date:   2016-03-10 08:30:58 -0600
categories: kernel
---
The normal behavior of the match operator is to rebind variables on the left side of the operator if there is a match. The pin operator `^` is used on the left side of the match operator when you don't wish to rebind and would like to match against the value of the pinned variable.

{% highlight elixir %}
a = 1

# rebind a to 2, then 3
a = 2
a = 3

# Match error because a is pinned to 3
^a = 4

{% endhighlight %}

Documentation: [Pin Operator](http://elixir-lang.org/getting-started/pattern-matching.html#the-pin-operator)
