---
layout: post
title:  "Sum an enumerable"
date:   2016-05-23 08:20:58 -0600
categories: ["Enum"]
---
This example shows how to sum a list, map, range, or other enumerable to calucate a total value.

{% highlight elixir %}

# Enum.sum/1 for numeric values
 6 == Enum.sum([1, 2, 3])
 6 == Enum.sum(1..3)
 
 # reduce to extract/transform a value during sum
 6 = Enum.reduce(%{ a: 1, b: 2, c: 3 }, 0, fn({_k, v}, acc) -> v + acc end)

{% endhighlight %}

Documentation:

- [Enum.sum/1](http://elixir-lang.org/docs/stable/elixir/Enum.html#sum/1)
- [Enum.reduce/3](http://elixir-lang.org/docs/stable/elixir/Enum.html#reduce/3)