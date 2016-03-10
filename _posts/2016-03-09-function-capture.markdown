---
layout: post
title:  "Function capturing"
date:   2016-03-09 20:30:58 -0600
categories: kernel
---
Elixir often refers to functions in the format `Module.function/arity`. For example the `to_atom` function in the `String` module which takes one argument would be referred to as `String.to_atom/1` in the documentation. When a reference to a function is needed, we can use the function capture syntax as shown below to get a reference to a function.

{% highlight elixir %}

fun_to_atom = &String.to_atom/1

:a = fun_to_atom.("a")

true = is_function(fun_to_atom)

# Function capturing is often used to pass functions as parameters
# to another function
[:a] = Enum.map(["a"], &String.to_atom/1)

{% endhighlight %}

Documentation: [Function Capturing](http://elixir-lang.org/getting-started/modules.html#function-capturing)
