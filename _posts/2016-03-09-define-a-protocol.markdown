---
layout: post
title:  "Define a Protocol"
date:   2016-03-09 013:20:58 -0600
categories: kernel
---
A Protocol is a way to dispatch to a particular implementation of a function based on the type of the parameter.

The macros `defprotocol` and `defimpl` are used to define Protocols and Protocol implementations for different types in the following example.
{% highlight elixir %}
defprotocol Double do

  def double(input)

end

defimpl Double, for: Integer do

  def double(int) do
    int * 2
  end

end


defimpl Double, for: List do

  def double(list) do
    list ++ list
  end

end

4 = Double.double(2)
[1, 2, 1, 2] = Double.double([1, 2])
{% endhighlight %}

Documentation: [Protocols](http://elixir-lang.org/getting-started/protocols.html)
