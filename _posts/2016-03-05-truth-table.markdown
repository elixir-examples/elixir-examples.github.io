---
layout: post
title:  "Truth table"
date:   2016-03-05 12:10:58 -0600
categories: kernel
---
The truth table for if/cond/unless statements in Elixir is simple: only nil and false evaluate to false. All other values are true.

{% highlight elixir %}
# Only nil and false are falsey everything else is truthy
nil
false
{% endhighlight %}
