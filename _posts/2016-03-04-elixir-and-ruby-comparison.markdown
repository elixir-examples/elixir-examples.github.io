---
layout: post
title:  "Elixir and Ruby Comparison"
date:   2016-03-04 06:20:58 -0600
categories: ["Blog Post"]
---
The following is a guide to help compare Elixir and Ruby syntax and implementations.

<style>
.custom-table
{
  border-collapse:collapse;
  border-color:#000000;
  border-style:solid;
  border-width:2px;
}

.custom-table td
{
  border-color:#cccccc;
  border-style:solid;
  border-width:1px;
}
</style>
<table class="custom-table">
  <tr>
    <th></th>
    <th>Ruby</th>
    <th>Elixir</th>
  </tr>
  <!--  -->
  <tr>
  <td>Characteristics</td>
  <td>
  Object-oriented, Imperative, Metaprogramming</td>
  <td>
  Functional, Actor Concurrency, Macros</td>
  </tr>
  <!--  -->
  <tr>
  <td>Typing</td>
  <td>Dynamic</td>
  <td>Dynamic</td>
  </tr>
  <!--  -->
  <tr>
  <td>Concurrency</td>
  <td>N/A</td>
  <td>Lightweight Processes</td>
  </tr>
  <!--  -->
  <tr>
  <td>Static Analysis</td>
  <td>
  Not Available</td>
  <td>
  Optional Typespecs</td>
  </tr>
  <!--  -->
  <tr>
  <td>Interfaces</td>
  <td>
  Duck Typing</td>
  <td>
  Behaviours & Protocols</td>
  </tr>
  <!--  -->
  <tr>
  <td>Package Manager</td>
  <td>RubyGems</td>
  <td>Hex</td>
  </tr>
  <!--  -->
  <tr>
  <td>Task Runner</td>
  <td>rake</td>
  <td>mix</td>
  </tr>
  <!--  -->
  <tr>
  <td>Interactive Shell</td>
  <td>irb</td>
  <td>iex</td>
  </tr>
  <!--  -->
  <tr>
  <td>Testing</td>
  <td>RSpec, test-unit, minitest</td>
  <td>ExUnit</td>
  </tr>
  <!--  -->
  <tr>
  <td>Web Framework</td>
  <td>Rails</td>
  <td>Phoenix</td>
  </tr>
  <!--  -->
  <tr>
  <td>Virtual Machine</td>
  <td>
  YARV</td>
  <td>
  BEAM</td>
  </tr>
  <!--  -->
  <tr>
  <td>Distributed Computing</td>
  <td>N/A</td>
  <td>Open Telecom Platform (OTP)</td>
  </tr>
<tr>
<td>Define a method/function</td>
<td>
{% highlight ruby %}
def hello
  "result"
end
{% endhighlight %}</td>
<td>
{% highlight elixir %}
def hello do
  "result"
end
{% endhighlight %}</td>
</tr>
<!--  -->
<td>Variable assignment/Capture</td>
<td>
{% highlight ruby %}
#
a = "hello"
{% endhighlight %}

</td>
<td>
{% highlight elixir %}
# match operator
a = "hello"
{% endhighlight %}
</td>
</tr>
<!--  -->
<tr>
<td>Hash/Map Syntax</td>
<td>
{% highlight ruby %}
{a: 1}
{% endhighlight %}</td>
<td>
{% highlight elixir %}
%{a: 1}
{% endhighlight %}</td>
</tr>
<!--  -->
<tr>
<td>Array/Tuple</td>
<td>
{% highlight ruby %}
[1, 2, 3, 4]
{% endhighlight %}</td>
<td>
{% highlight elixir %}
{1, 2, 3, 4}
{% endhighlight %}</td>
</tr>
<!--  -->
<tr>
<td>List Syntax</td>
<td>
{% highlight ruby %}
# Not Available
{% endhighlight %}</td>
<td>
{% highlight elixir %}
[1, 2, 3, 4]
{% endhighlight %}</td>
</tr>
<!--  -->
<tr>
<td>Map an Array/List</td>
<td>
{% highlight ruby %}
[1, 2, 3, 4].map { |x| x * x }
{% endhighlight %}</td>
<td>
{% highlight elixir %}
Enum.map([1, 2, 3, 4], &(&1 * &1))
{% endhighlight %}</td>
</tr>
<!--  -->
<tr>
<td>Range Syntax</td>
<td>
{% highlight ruby %}
1..4
{% endhighlight %}</td>
<td>
{% highlight elixir %}
1..4
{% endhighlight %}</td>
</tr>
<!--  -->
<tr>
<td>String Interpolation</td>
<td>
{% highlight ruby %}
"#{2 + 2}"
{% endhighlight %}</td>
<td>
{% highlight elixir %}
"#{2 + 2}"
{% endhighlight %}</td>
</tr>
<!--  -->
<tr>
<td>Reverse a String</td>
<td>
{% highlight ruby %}
"hello".reverse
{% endhighlight %}</td>
<td>
{% highlight elixir %}
String.reverse("hello")
{% endhighlight %}</td>
</tr>
<!--  -->
<td>Define a class</td>
<td>
{% highlight ruby %}
class Hello
end
{% endhighlight %}</td>
<td>
{% highlight elixir %}
# Not Applicable
# Modules, Structs, Protocols are used
{% endhighlight %}</td>
</tr>
<!--  -->
<tr>
<td>Anonymous Functions</td>
<td>
{% highlight ruby %}
square = lambda { |x| x * x }
{% endhighlight %}</td>
<td>
{% highlight elixir %}
square = fn(x) -> x * x end
{% endhighlight %}</td>
</tr>
<!--  -->
<td>Call Anonymous Function</td>
<td>
{% highlight ruby %}
square.call(2)
square.(2)
{% endhighlight %}</td>
<td>
{% highlight elixir %}
square.(2)
{% endhighlight %}</td>
</tr>
<!--  -->
<tr>
<td>Define Module</td>
<td>
{% highlight ruby %}
module Example
end
{% endhighlight %}</td>
<td>
{% highlight elixir %}
defmodule Example
end
{% endhighlight %}</td>
</tr>
<!--  -->
<tr>
<td>Atoms</td>
<td>
{% highlight ruby %}
#
:one
{% endhighlight %}</td>
<td>
{% highlight elixir %}
# not garbage collected
:one
{% endhighlight %}</td>
</tr>
<!--  -->
<tr>
<td>Division</td>
<td>
{% highlight ruby %}
#
5 / 2 == 2
{% endhighlight %}</td>
<td>
{% highlight elixir %}
# use div/2 for integer division
 5 / 2 == 2.5
{% endhighlight %}</td>
</tr>
<!--  -->
<tr>
<td>If</td>
<td>
{% highlight ruby %}
if true
end
{% endhighlight %}</td>
<td>
{% highlight elixir %}
if true do
end
{% endhighlight %}</td>
</tr>
<!--  -->
<tr>
<td>Else If</td>
<td>
{% highlight ruby %}
result = if 0 > 1
           "No"
         elsif 0 > 2
           "Nope"
         else
           "fallback"
         end
{% endhighlight %}</td>
<td>
{% highlight elixir %}
result = cond do
           0 > 1 -> "No"
           0 > 2 -> "Nope"
           true  -> "fallback"
         end
#
#
{% endhighlight %}</td>
</tr>
<!--  -->
<tr>
<td>Printing</td>
<td>
{% highlight ruby %}
puts "Hello World"
{% endhighlight %}</td>
<td>
{% highlight elixir %}
IO.puts "Hello World"
{% endhighlight %}</td>
</tr>
<!--  -->
<tr>
<td>Looping</td>
<td>
{% highlight ruby %}
[1, 2, 3, 4].each { |i| puts i }
{% endhighlight %}</td>
<td>
{% highlight elixir %}
Enum.each([1, 2, 3, 4], &(IO.puts &1))
{% endhighlight %}</td>
</tr>

<!--  -->
<tr>
<td></td>
<td>
{% highlight ruby %}
{% endhighlight %}</td>
<td>
{% highlight elixir %}
{% endhighlight %}</td>
</tr>
<!--  -->
<tr>
<td>Pattern Matching</td>
<td>
{% highlight ruby %}
# Not available
#
#
#
#
{% endhighlight %}</td>
<td>
{% highlight elixir %}
[a, b] = [1, 2]
%{a: value} = %{a: 1}
# pattern matching can match against literals
# and be used in function definitions,
# case statements, list comprehensions and more
{% endhighlight %}</td>
</tr>
<!--  -->
<tr>
<td>Guard Clauses</td>
<td>
{% highlight ruby %}
# not available
#
{% endhighlight %}</td>
<td>
{% highlight elixir %}
def hello( v ) when is_atom(v) do
end
{% endhighlight %}</td>
</tr>
<!--  -->
<tr>
<td>Metaprogramming</td>
<td>
{% highlight ruby %}
method_missing
define_method
# et al
{% endhighlight %}</td>
<td>
{% highlight elixir %}
# Macros
#
#
{% endhighlight %}</td>
</tr>
<!--  -->
<tr>
<td></td>
<td>
{% highlight ruby %}
{% endhighlight %}</td>
<td>
{% highlight elixir %}
{% endhighlight %}</td>
</tr>
<!--  -->
<tr>
<td></td>
<td>
{% highlight ruby %}
{% endhighlight %}</td>
<td>
{% highlight elixir %}
{% endhighlight %}</td>
</tr>
</table>
