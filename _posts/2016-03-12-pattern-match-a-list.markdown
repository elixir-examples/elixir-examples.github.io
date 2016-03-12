---
layout: post
title:  "Pattern match a list"
date:   2016-03-12 08:10:58 -0600
categories: list
---
This example shows examples of how a list can be pattern matched.

{% highlight elixir %}
[head|tail] = [1, 2, 3]
head = 1
tail = [2, 3]

[head|tail] = [1]
head = 1
tail = []

[] = []

# This does not match, no value for head
[head|tail] = []

# match head value
[1 | tail ]= [1, 2, 3]
tail = [2, 3]

# use underscore to ignore a variable
[head | _ ]= [1, 2, 3]
{% endhighlight %}
