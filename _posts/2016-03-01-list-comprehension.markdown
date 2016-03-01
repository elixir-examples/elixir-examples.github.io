---
layout: post
title:  "List comprehension"
date:   2016-03-01 08:00:58 -0600
categories: list
---
List comprehension

{% highlight elixir %}
[2, 4, 6] = for n <- [1, 2, 3], do: n + n
{% endhighlight %}

Related Documentation: [Comprehensions](http://elixir-lang.org/getting-started/comprehensions.html)
