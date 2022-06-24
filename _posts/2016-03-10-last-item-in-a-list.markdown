---
layout: post
title:  "Get the last item in a list"
date:   2016-03-10 11:37:58 -0600
categories: list
---
This example shows how to get the last item in a list. Keep in mind that it is more effecient to get the head of a list than the last item when processing lists.

{% highlight elixir %}

:c = List.last([:a, :b, :c])

# nil is returned for an empty list
nil = List.last([])

{% endhighlight %}

Documentation: [List.last/1](https://hexdocs.pm/elixir/List.html#last/1)
