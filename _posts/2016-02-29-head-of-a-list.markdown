---
layout: post
title:  "Head of a list"
date:   2016-02-29 02:37:58 -0600
categories: list
---
Get the head of a list

{% highlight elixir %}
1 = hd([1, 2, 3, 4])

# alternatively use pattern matching
[head | tail] = [1, 2, 3, 4]
# head contains 1
{% endhighlight %}
