---
layout: post
title:  "Anonymous functions"
date:   2016-03-02 12:10:58 -0600
categories: kernel
---
These examples show two syntaxes available to create anonymous functions.

{% highlight elixir %}
square = fn(x) -> x * x end

# calling an anonymous function uses a period
# before the parentheses
4 = square.(2)


# pattern matching the arguments can be used
first = fn([head|rest]) -> head end
1 = first.([1, 2])

# anonymous functions are commonly used as arguments
# to other functions
[1, 4, 9] = Enum.map([1, 2, 3], square)
[3, 4, 5] = Enum.map([1, 2, 3], fn(x) -> x + 2 end)
{% endhighlight %}


The shorthand syntax to create anonymous functions with the capture operator.
The syntax wraps an expression with `&()` and each argument is indexed starting at 1 identified by `&1`, `&2`, and so on.
{% highlight elixir %}
square = &( &1 * &1 )
4 = square.(2)

# This results in a compile error with
# the capture operator
# because at least one argument must be used
four = &(2 + 2)
{% endhighlight %}

Documentation [Capture operator](http://elixir-lang.org/docs/stable/elixir/Kernel.SpecialForms.html#&/1)
