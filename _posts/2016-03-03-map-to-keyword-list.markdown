---
layout: post
title:  "Map to keyword list"
date:   2016-03-03 08:12:58 -0600
categories: map
---
Convert a map to keyword list

{% highlight elixir %}
[one: 1, two: 2] = Map.to_list(%{one: 1, two: 2})
{% endhighlight %}
