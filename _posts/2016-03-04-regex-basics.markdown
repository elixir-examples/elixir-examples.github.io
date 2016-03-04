---
layout: post
title:  "Regex basics"
date:   2016-03-04 02:20:58 -0600
categories: regex
---
Here are a few examples on how to use regular expressions in Elixir.

{% highlight elixir %}
# A regex sigil to match 'foo'
~r/foo/

# Interpolation can be used
~r/foo/ = ~r/#{"foo"}/

# Test if a string matches
true = Regex.match?( ~r/foo/ , "Hello foo")

# Run returns first match
["foo1", "1"] = Regex.run(~r/foo([0-9])/, "foo1 foo2")

# Scan returns all matches
[["foo1", "1"], ["foo2", "2"]] = Regex.scan(~r/foo([0-9])/, "foo1 foo2")

# Replace matches in a string
"one_two_three" = Regex.replace(~r/-/, "one-two-three", "_")
{% endhighlight %}


Documentation: [Regex](http://elixir-lang.org/docs/stable/elixir/Regex.html)
