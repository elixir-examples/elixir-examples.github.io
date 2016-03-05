---
layout: post
title:  "Check if a file exists"
date:   2016-03-05 17:10:58 -0600
categories: file
---
The `File` module provides an `exists?/1` to check if a file exists.

{% highlight elixir %}
true  = File.exists?("exists.txt")
false = File.exists?("doesnt_exist.txt")
{% endhighlight %}
