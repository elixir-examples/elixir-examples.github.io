---
layout: post
title:  "Update a map value"
date:   2016-02-29 02:32:58 -0600
categories: map
---
Update a map value

{% highlight elixir %}
%{example_key: "New Value"} = %{  %{ example_key: "Old Value" } | example_key: "New Value" }
{% endhighlight %}
