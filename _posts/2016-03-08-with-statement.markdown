---
layout: post
title:  "With statement"
date:   2016-03-08 20:30:58 -0600
categories: kernel
---

The special form `with` is used to chain a sequence of matches in order and finally return the result of `do:` if all the clauses match. However, if one of the clauses does not match, its result is immediately returned.

{% highlight elixir %}
6 = with { parsed, _ } <- Integer.parse("3.0"),
         do: parsed * 2

# if a clause doesn't match
# it's result is immediately returned
6 = with 2 <- 2,
         1 <- 6,
         do: 11       

:error = with { parsed, _ } <- Integer.parse("WORD"),
         do: parsed * 2
{% endhighlight %}


Documentation: [Kernel.SpecialForms.with/1](https://hexdocs.pm/elixir/Kernel.SpecialForms.html#with/1)
