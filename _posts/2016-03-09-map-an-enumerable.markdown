---
layout: post
title:  "Map an enumerable"
date:   2016-03-09 08:30:58 -0600
categories: ["Enum"]
---
The `map` function enumerates an enumerable while applying a transform function and collects the results into a list. `Enum.map` can be used to map a list, map a map, or map any enumerable.

{% highlight elixir %}
[2, 4, 6] = Enum.map([1, 2, 3], fn(i) -> i * 2 end)

# map a map
[:one, :two] = Enum.map(%{ one: 1, two: 2}, fn({k, v}) -> k end)

# map a keyword list
[1, 2] = Enum.map([c: 1, d: 2], fn({k, v}) -> v end)

# map to a keyword list
[a: 2, a: 4, a: 6] = Enum.map([1, 2, 3], fn(i) -> {:a , i * 2} end)

{% endhighlight %}

Documentation: [Enum.map/2](http://elixir-lang.org/docs/stable/elixir/Enum.html#map/2)
