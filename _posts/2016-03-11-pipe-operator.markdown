---
layout: post
title:  "Pipe operator"
date:   2016-03-11 14:03:58 -0600
categories: kernel
---

The pipe operator `|>` is used to chain together a sequence of function calls. The result of the expression on the left side of the operator is passed as the first argument to the function in the right side of the operator.

{% highlight elixir %}
["A", "B", "C"] = "a,b,c"
                   |> String.split(",") # split takes 2 arguments but here
                                        # the first argument is omitted
                                        # in the parentheses and
                                        # the left side of the |> operator
                                        # will be the first argument implicitly
                   |> Enum.map( &String.upcase/1 )

# This is equivalent to:
Enum.map(String.split("a,b,c", ","), &String.upcase/1)
{% endhighlight %}
