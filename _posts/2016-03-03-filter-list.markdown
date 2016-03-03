---
layout: post
title:  "Filter list"
date:   2016-03-03 11:30:58 -0600
categories: list
---
Filter a list

{% highlight elixir %}
[3, 4] = Enum.filter( [1, 2, 3, 4], fn(x) -> x > 2 end )
{% endhighlight %}
