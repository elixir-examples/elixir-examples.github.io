---
layout: post
title:  "Get a value from a map"
date:   2016-03-05 08:20:58 -0600
categories: map
---
This example shows different ways to get values from a map.

{% highlight elixir %}
# dot syntax can be used if key is atom
1 = %{c: 1}.c

# Raises a key error for missing key
%{c: 1}.a

# [] works for non-atom values
1 = %{"a" => 1}["a"]

# [] returns nil for missing values
nil = %{"a" => 1}["b"] 

# Pattern matching can be used
%{c: value} = %{c: 1}

1   = Map.get(%{c: 1}, :c)
nil = Map.get(%{c: 1}, :a)

# Default value can be specified
# for when the key is misssing
"default" = Map.get(%{c: 1}, :a, "default")

{:ok, value} = Map.fetch(%{c: 1}, :c)
:error       = Map.fetch(%{c: 1}, :a)

1 = Map.fetch!(%{c: 1}, :c)

# Raises a key error
Map.fetch!(%{c: 1}, :a)
{% endhighlight %}
