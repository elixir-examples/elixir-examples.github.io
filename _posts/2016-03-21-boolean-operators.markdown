---
layout: post
title:  "Boolean operators - and, or, &&, ||"
date:   2016-03-21 07:00:58 -0600
categories: Kernel
---

Elixir provides short-circuiting logical boolean operators `and`, `or`, `&&`, and  `||`. The `and` and `or` operators are said to be strict because they only accept booleans and return a boolean result.  The pipes `||` and ampersands `&&` are non-strict/relaxed and can take any value. The values `false` and `nil` are the only falsey values and everything else is true.

Use `and` or `or` when you have boolean inputs and want a boolean result.

{% highlight elixir %}
false = false and true
true  = true  and true

true  = true  or false
false = false or false

# A non boolean argument results in an ArgumentError
"hello" and true

# || can be used to assign fallback/default values
"default" = nil || "default"

# short-circuted || result since left side being
# true makes it true
"first" = "first" || "second"

"second" = "first" && "second"
# short-circuted && result, left-side false value returned
false = false && "second"

{% endhighlight %}



 Documentation: [Basic Operators](http://elixir-lang.org/getting-started/basic-operators.html)
