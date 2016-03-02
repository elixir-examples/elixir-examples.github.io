---
layout: post
title:  "Cond statement"
date:   2016-03-02 12:08:58 -0600
categories: kernel
---
cond - similar to `if, else if, else` in other languages

{% highlight elixir %}
"true is always true" = cond do
                           0 > 1 -> "No"
                           0 > 2 -> "Nope"
                           true  -> "true is always true"
                        end
{% endhighlight %}
