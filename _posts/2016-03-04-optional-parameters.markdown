---
layout: post
title:  "Optional parameters"
date:   2016-03-04 08:50:58 -0600
categories: kernel
---
You can define a method with default arguments using the `\\` syntax. The default arguments are used when the argument is not provided.
{% highlight elixir %}
def hello(name \\ "Unknown" ) do
  # name value is "Unknown" when name argument not provided
  "Hello #{name}"
end
{% endhighlight %}
