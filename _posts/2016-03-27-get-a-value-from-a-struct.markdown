---
layout: post
title:  "Get a value from a struct"
date:   2016-03-27 08:20:58 -0600
categories: ["Struct"]
---
This example shows how to get a value from a struct field.

{% highlight elixir %}

# Define a struct for this example
defmodule User do
  defstruct email: nil
end

# dot syntax
"c@c.com" = %User{email: "c@c.com"}.email

# Underlying implementation is a map
# So Map methods work
"c@c.com" = Map.get(%User{email: "c@c.com"}, :email)

# Pattern match to get a value
%{ email: email }   = %User{email: "c@c.com"}
%User{email: email} = %User{email: "c@c.com"}

# Access protocol not available by default
%User{email: "c@c.com"}[:email]
#** (UndefinedFunctionError) undefined function User.fetch/2 (User does not implement the Access behaviour)
#             User.fetch(%User{email: "c@c.com"}, :email)
#    (elixir) lib/access.ex:118: Access.fetch/2
#    (elixir) lib/access.ex:149: Access.get/3


# Enumerable protocol not available by default
Enum.filter( %User{email: "c@c.com"}, fn({key, _}) -> key == :email  end)
#** (Protocol.UndefinedError) protocol Enumerable not implemented for %User{email: "c@c.com"}
#    (elixir) lib/enum.ex:1: Enumerable.impl_for!/1
#    (elixir) lib/enum.ex:116: Enumerable.reduce/3
#    (elixir) lib/enum.ex:1477: Enum.reduce/3
#    (elixir) lib/enum.ex:742: Enum.filter/2

{% endhighlight %}

Documentation:

- [Structs](http://elixir-lang.org/getting-started/structs.html)
