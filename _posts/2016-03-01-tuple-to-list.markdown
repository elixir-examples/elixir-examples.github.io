---
layout: post
title:  "Tuple to list"
date:   2016-03-01 08:02:58 -0600
categories: tuple
---
Tuple to list

{% highlight elixir %}
[:a, :b, :c] = Tuple.to_list({:a, :b, :c})
{% endhighlight %}

Documentation: [Tuple.to_list/1](http://elixir-lang.org/docs/stable/elixir/Tuple.html#to_list/1)
