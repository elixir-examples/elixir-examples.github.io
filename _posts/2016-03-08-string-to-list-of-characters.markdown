---
layout: post
title:  "String to list of single character strings"
date:   2016-03-08 08:30:58 -0600
categories: string
---
This example shows how to convert a String into a list of single characters. This could be used to enumerate a string.

Elixir calls each character a grapheme so we use the `String.graphemes/1` method.
{% highlight elixir %}
["T", "e", "s", "t"] = String.graphemes("Test")

# Contrast this with codepoints which may return
# multiple codepoints for a single character
["ö"]      = String.graphemes("ö")
["o", "̈"] = String.codepoints("ö")

{% endhighlight %}

Documentation: [String.graphemes/1](https://hexdocs.pm/elixir/String.html#graphemes/1)
