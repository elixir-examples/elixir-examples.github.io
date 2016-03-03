---
layout: post
title:  "Mix Ecto Rollback Command"
date:   2016-03-02 08:08:58 -0600
categories: ecto
---
This mix task reverts migrations which were previously run.

{% highlight elixir %}
mix ecto.rollback
{% endhighlight %}

Documentation: [mix ecto.rollback](https://hexdocs.pm/ecto/Mix.Tasks.Ecto.Rollback.html)

See Also:

- [mix ecto.migrate](/examples/mix-ecto-migrate-command)
- [mix ecto.gen.migration](/examples/mix-generate-ecto-migration)
