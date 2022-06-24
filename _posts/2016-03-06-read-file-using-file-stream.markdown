---
layout: post
title:  "Read file using File.stream!"
date:   2016-03-06 08:20:58 -0600
categories: file
---
This example shows how to read a file using `File.stream!/3`.

{% highlight elixir %}
stream = File.stream!("scratch.txt")

# The stream is read by each line when Enumerated
Enum.each(stream, fn(x) -> IO.puts x end)

["Line 1\n", "Line 2\n"] = Enum.into(stream, [])

2 = Enum.reduce(stream, 0, fn(x, acc) -> acc + 1 end)
{% endhighlight %}

See documentation for more information: [File.stream!/3](https://hexdocs.pm/elixir/File.html#stream!/3)
