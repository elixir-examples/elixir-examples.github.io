---
layout: post
title:  "Update a struct field"
date:   2016-03-25 08:20:58 -0600
categories: ["Struct"]
---
This example shows how to update a struct field.

{% highlight elixir %}

# Define a struct for this example
defmodule User do
  defstruct email: nil
end

%User{email: "c@c.com"} = struct(%User{}, email: "c@c.com")

# Structs are based on maps
# so map update methods and syntax are valid
%User{email: "a@a.co"} = %{ %User{} | email: "a@a.co" }

%User{email: "b@b.com"} = Map.put(%User{}, :email, "b@b.com")
{% endhighlight %}

Documentation:

- [Structs](http://elixir-lang.org/getting-started/structs.html)
- [Kernel.struct/2](https://hexdocs.pm/elixir/Kernel.html#struct/2)
