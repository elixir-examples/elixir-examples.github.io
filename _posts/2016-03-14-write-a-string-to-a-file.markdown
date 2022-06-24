---
layout: post
title:  "Write a string to file"
date:   2016-03-14 07:10:58 -0600
categories: file
---
This example shows how to write to a file using `File.write`.

{% highlight elixir %}
:ok = File.write("example.txt","Hello File!")

# Error tuple for failure
{:error, reason} = File.write("example.txt","Hello File!")

# write!/3 Raises exception
:ok = File.write!("example2.txt","Hello File!")
{% endhighlight %}

Documentation: [File.write/3](https://hexdocs.pm/elixir/File.html#write/3)
