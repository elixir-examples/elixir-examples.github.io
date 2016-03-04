---
layout: post
title:  "Range syntax"
date:   2016-03-04 08:50:58 -0600
categories: range
---
This example shows the literal syntax used to create a range.

{% highlight elixir %}
# range is inclusive start to end
1..4

[1, 2, 3, 4] = Enum.to_list( 1..4 )

# can be defined high to low
4..1
{% endhighlight %}

Documentation: [Range](http://elixir-lang.org/docs/stable/elixir/Range.html)
