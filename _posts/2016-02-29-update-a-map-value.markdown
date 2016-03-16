---
layout: post
title:  "Update a map value"
date:   2016-02-29 02:32:58 -0600
categories: map
---
Update a map value

{% highlight elixir %}
%{a: "New Value"} = %{  %{ a: "Old Value" } | a: "New Value" }

# Note that this does not work to add a new key
%{ %{} | new_key: 1}
# Raises (KeyError) key :new_key not found in: %{}
{% endhighlight %}
