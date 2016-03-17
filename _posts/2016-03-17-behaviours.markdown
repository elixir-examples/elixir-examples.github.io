---
layout: post
title:  "Behaviours"
date:   2016-03-17 08:10:58 -0600
categories: Kernel
---

Behaviours provide a way to define an interface which a module can implement. A module which declares that it implements the Behaviour with the `@behaviour` annotation will be checked at compile time.

{% highlight elixir %}
# The @callback annotations below define what methods a module
# needs to implement the behaviour. The parameter and return types
# must be specified or a compile error will occur.
defmodule Greeter do
  @callback say_hello(String.t) :: any
  @callback say_goodbye(String.t) :: any
end

# A module uses the @behaviour annotation to indicate
# that it implements a behaviour
defmodule NormalGreeter do
  @behaviour Greeter
  def say_hello(name), do: IO.puts "Hello, #{name}"
  def say_goodbye(name), do: IO.puts "Goodbye, #{name}"
end

defmodule ExcitedGreeter do
  @behaviour Greeter
  def say_hello(name), do: IO.puts "Hello, #{name}!!"
  def say_goodbye(name), do: IO.puts "Goodbye, #{name}!!"
end

# Since this does not implement `say_goodbye/1`
# a compile time warning will occur:
# "warning: undefined behaviour function say_goodbye/1 (for behaviour Greeter)"
defmodule InvalidGreeter do
  @behaviour Greeter
  def say_hello(name), do: IO.puts "Hello, #{name}."
end

{% endhighlight %}



 Documentation: [Behaviours](http://elixir-lang.org/getting-started/typespecs-and-behaviours.html#behaviours)
