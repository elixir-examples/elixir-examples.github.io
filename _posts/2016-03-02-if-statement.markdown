---
layout: post
title:  "If statement"
date:   2016-03-02 08:07:58 -0600
categories: kernel
---
If statement

{% highlight elixir %}
"good" = if true do
 			"good"
   		 else
 			"This will"
   		 end

# nil is default when else is missing
nil = if false do
 			"good"
   		   end 		 

# alternative, one line syntax  		 
"good" = if true, do: "good"
"else"  = if false, do: "good", else: "else"
{% endhighlight %}

Documentation: [Kernel.if/2](https://hexdocs.pm/elixir/Kernel.html#if/2)

See Also: [unless](/examples/unless-statement)
