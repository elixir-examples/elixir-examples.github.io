---
layout: post
title:  "Pattern match a map"
date:   2016-03-03 08:10:58 -0600
categories: map
---
Pattern match a map

{% highlight elixir %}
%{ b: value, d: value2 } = %{ a: 1, b: 2, d: 3 }

# raises a map error if key is missing
%{ c: value } = %{ a: 1, b: 2 }
{% endhighlight %}
