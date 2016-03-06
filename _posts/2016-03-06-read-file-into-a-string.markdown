---
layout: post
title:  "Read file into a string"
date:   2016-03-06 08:03:58 -0600
categories: file
---
This example shows how to read a file to a string.

{% highlight elixir %}
{:ok, contents} = File.read("exists.txt")
{:error, reason} = File.read("doesnt_exist.txt")

contents = File.read!("exists.txt")

# Raises a File.Error
contents = File.read!("doesnt_exist.txt")
{% endhighlight %}
