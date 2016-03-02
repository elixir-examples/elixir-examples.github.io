---
layout: post
title:  "Anonymous functions"
date:   2016-03-02 12:10:58 -0600
categories: kernel
---
Anonymous function syntax

{% highlight elixir %}
square = fn(x) -> x * x end

# calling an anonymous function
4 = square.(2)

# shorthand syntax
square = &( &1 * &1 )
{% endhighlight %}
