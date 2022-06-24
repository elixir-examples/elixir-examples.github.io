---
layout: post
title:  "case statement"
date:   2016-03-01 08:07:58 -0600
categories: kernel
---
Case statement (similar to switch in other languages)

{% highlight elixir %}
"Good" = case {:ok, :data} do
              {:ok, result} -> "Good"
           {:error, result} -> "Bad"
                          _ -> "Nothing matched"
         end
{% endhighlight %}

Documentation: [Kernel.SpecialForms.case/2](https://hexdocs.pm/elixir/Kernel.SpecialForms.html#case/2)
