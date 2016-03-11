---
layout: post
title:  "Alias, Use, Import, and Require"
date:   2016-03-11 08:30:58 -0600
categories: kernel
---

The special forms `alias`, `use`, `import`, and `require` are ways of accessing functions or macros outside of the current module. The forms `alias` and `import` are used to be able to refer to functions without having to use their fully qualified names. The form `use` is used to add functionality to the current module by running a macro from another module. When macros are used from an external module, `require` is needed to make the macros available to the compiler at compile time.

## Alias
Used to shorten the references to a specific module.
{% highlight elixir %}
# Fully qualified User struct
%Application.User{}

# alias is used to shorten the fully qualified name
alias Application.User, as: User

# After aliasing
%User{}

# alias without `:as` option will automatically use the last
# part of the module name after the last period
alias Application.User
# is the same as
alias Application.User, as: User
{% endhighlight %}

## Use
Adds functionality to the current module by calling another module's `__using__` macro.

{% highlight elixir %}
defmodule Hello do
  defmacro __using__(_opts) do
    quote do
      def say_hello do
        IO.puts "Hello"
      end
    end
  end
end

defmodule MyModule do
  use Hello
end

# prints "Hello"
MyModule.say_hello
{% endhighlight %}

## Import
Imports specific functions into the current module so they can be called without using their module name.
{% highlight elixir %}
# Without import functions need to be called
# by their full name including the module
"ABC" = String.upcase("abc")

# Import a single function with the form
# import Module, only: [function_name: arity]
import String, only: [upcase: 0]

# upcase can now be used without the module name
"ABC" = upcase("abc")

# Imports all functions in the String module.
# It is recommend to use only option above to
# only import the functions you need.
import String
{% endhighlight %}

## Require
Makes a macro from an external module available to the compiler at compile time.

{% highlight elixir %}
defmodule Hello do
  # Example macro to add say_hello function to the module
  defmacro hello_macro do
    quote do
      def say_hello do
        IO.puts "Hello"
      end
    end
  end

end


defmodule MyModule do
  # Without require here results in the following error:
  # (CompileError) iex:37: you must require Hello before invoking the macro Hello.hello_macro/0
  require Hello
  Hello.hello_macro

end

# Prints Hello
MyModule.say_hello
{% endhighlight %}


See documentation for more information: [Alias, require and import](http://elixir-lang.org/getting-started/alias-require-and-import.html)
