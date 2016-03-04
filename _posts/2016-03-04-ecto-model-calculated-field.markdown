---
layout: post
title:  "Ecto model calculated field"
date:   2016-03-04 08:40:58 -0600
categories: ecto
---
This example shows a common approach to having a calculated field for a model.

{% highlight elixir %}
defmodule User do
  use Ecto.Schema

  schema "users" do
    field :first_name, :string
    field :last_name,  :string
  end

  # Example calculated field
  def full_name(user) do
      user.first_name <> " " <> user.last_name
  end

end
{% endhighlight %}
