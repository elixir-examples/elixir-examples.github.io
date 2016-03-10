---
layout: post
title:  "Mix list all tasks command"
date:   2016-03-10 13:30:58 -0600
categories: mix
---
The `mix help` command can be used to list all available commands. Available commands will vary depending if there is a `mix.exs` file in the current directory.
{% highlight bash %}
$ mix help
mix                   # Runs the default task (current: "mix run")
mix app.start         # Starts all registered apps
mix archive           # Lists all archives
mix archive.build     # Archives this project into a .ez file
mix archive.install   # Installs an archive locally
mix archive.uninstall # Uninstalls archives
mix clean             # Deletes generated application files
mix cmd               # Executes the given command
mix compile           # Compiles source files
mix deps              # Lists dependencies and their status
mix deps.clean        # Deletes the given dependencies' files
mix deps.compile      # Compiles dependencies
mix deps.get          # Gets all out of date dependencies
mix deps.unlock       # Unlocks the given dependencies
mix deps.update       # Updates the given dependencies
mix do                # Executes the tasks separated by comma
mix escript.build     # Builds an escript for the project
mix help              # Prints help information for tasks
mix hex               # Prints Hex help information
mix hex.build         # Builds a new package version locally
mix hex.config        # Reads or updates Hex config
mix hex.docs          # Publishes docs for package
mix hex.info          # Prints Hex information
mix hex.key           # Hex API key tasks
mix hex.outdated      # Shows outdated Hex deps for the current project
mix hex.owner         # Hex package ownership tasks
mix hex.publish       # Publishes a new package version
mix hex.registry      # Hex registry tasks
mix hex.search        # Searches for package names
mix hex.user          # Hex user tasks
mix loadconfig        # Loads and persists the given configuration
mix local             # Lists local tasks
mix local.hex         # Installs Hex locally
mix local.public_keys # Manages public keys
mix local.rebar       # Installs rebar locally
mix new               # Creates a new Elixir project
mix phoenix.new       # Create a new Phoenix v0.13.1 application
mix profile.fprof     # Profiles the given file or expression with fprof
mix run               # Runs the given file or expression
mix test              # Runs a project's tests
iex -S mix            # Starts IEx and run the default task
{% endhighlight %}
