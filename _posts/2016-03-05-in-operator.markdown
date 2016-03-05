---
layout: post
title:  "In operator"
date:   2016-03-05 17:20:58 -0600
categories: kernel
---
The `in` operator tests for membership using `===` within an enumerable.

{% highlight elixir %}

true = "one" in ["one", "two"]

# `in` is equivalent to calling Enum.member?/2
Enum.member?(["one", "two"], "one")

true = {:a, 1} in %{a: 1, b: 2}
true = 1 in 1..4
{% endhighlight %}
