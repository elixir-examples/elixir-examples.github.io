---
layout: post
title:  "Map to struct"
date:   2016-03-03 08:11:58 -0600
categories: map
---
Map to struct

{% highlight elixir %}
# given the struct
defmodule User do
  defstruct username: nil
end

%User{username: "test" } = struct(User, %{username: "test", password: "secret"})

# struct! raises KeyError if un-matching keys provided
%User{username: "test" } = struct!(User, %{username: "test", password: "secret"})
{% endhighlight %}
