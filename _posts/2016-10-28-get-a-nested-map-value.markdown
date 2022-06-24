---
layout: post
title:  "Get a value from nested maps"
date:   2016-10-28 02:32:58 -0600
categories: map
---
The `get_in` function can be used to retrieve a nested value in nested maps using a list of keys.

{% highlight elixir %}
nested = %{ one: %{ two: 3} }

3 = get_in(nested, [:one, :two])

# Returns nil for missing value
nil = get_in(nested, [:one, :three])

{% endhighlight %}


Documentation:

- [Kernel.get_in/2](https://hexdocs.pm/elixir/Kernel.html#get_in/2)