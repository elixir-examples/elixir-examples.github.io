---
layout: post
title:  "function definition"
date:   2016-03-03 02:50:58 -0600
categories: kernel
---
How to define a function/method in elixir:

{% highlight elixir %}
# functions are defined inside Modules
defmodule Examples do

  # basic defintion
  def do_stuff( params ) do
      "result"
  end

  #shorthand syntax
  def shorthand(), do: "result"

  # defp is for private functions
  defp private_method, do: "private"

  # params can pattern match
  def match_this(%{:key => value}), do: value

  # the first matching function is called (order matters)
  def test(test), do: "matches any param"
  def test([]), do: "never matched"

end
{% endhighlight %}
