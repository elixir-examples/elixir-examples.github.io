---
layout: post
title:  "Phoenix Framework from HTTP Request to Response"
date:   2016-03-15 08:10:58 -0600
categories: ["Blog Post"]
---

This post describes the steps that a HTTP request/response takes in a Phoenix Framework application. The example application described here was generated using the command `mix phoenix.new hello_world`.

The steps in the HTTP request/response cycle are outlined as follows:

* HTTP Request
* Cowboy
    * Plug
        * Phoenix Endpoint
            * Phoenix Router
            * Phoenix Controller
            * Phoenix View
            * Phoenix Template
* HTTP Response

# HTTP Request
A browser user sends an HTTP GET request to `http://localhost:4000/`.

The request is received by the Cowboy server.

# Cowboy
Cowboy is an Erlang based HTTP server which is currently the only server with a Plug adapter implemented.

Cowboy will parse the HTTP request and the first Plug Connection will be created in Plug's Cowboy adapter.

# Plug
Plug is a web server interface for Elixir that provides a way to compose modules in a sequence during a request/response cycle.

Each plug module receives the HTTP request which is called a Plug Connection and often referred to as the variable `conn`. The plug may transform and update the connection and then return an HTTP response immediately or pass the connection to the next plug in the sequence.

The Plug library has built in plugs that provide CSRF protection, sessions, logging, serving static files, and more.

Phoenix applications themselves are built by composing a series of plugs which are defined in a Phoenix Endpoint.

# Phoenix Endpoint
The Phoenix Endpoint is found in the  project file `lib/hello_world/endpoint.ex`. The endpoint defines the plugs that will make up your application.  It is the entry and exit point to the Phoenix application.

Each plug will be called in order as defined in the `HelloWorld.Endpoint`. A plug such as the `Plug.Static` plug may send a response before the connection is seen by other plugs. Note that the last plug defined is the router.

{% highlight elixir %}
defmodule HelloWorld.Endpoint do
  use Phoenix.Endpoint, otp_app: :hello_world

  # Serve at "/" the static files from "priv/static" directory.
  #
  # You should set gzip to true if you are running phoenix.digest
  # when deploying your static files in production.
  plug Plug.Static,
    at: "/", from: :hello_world, gzip: false,
    only: ~w(css images js favicon.ico robots.txt)

  # Code reloading can be explicitly enabled under the
  # :code_reloader configuration of your endpoint.
  if code_reloading? do
    plug Phoenix.LiveReloader
    plug Phoenix.CodeReloader
  end

  plug Plug.Logger

  plug Plug.Parsers,
    parsers: [:urlencoded, :multipart, :json],
    pass: ["*/*"],
    json_decoder: Poison

  plug Plug.MethodOverride
  plug Plug.Head

  plug Plug.Session,
    store: :cookie,
    key: "_hello_world_key",
    signing_salt: "0yg9mHDO"

  plug :router, HelloWorld.Router
end

{% endhighlight %}

# Phoenix Router

A Router defines an application's pipelines and paths. If the given URL path matches based on the HTTP verb and path, the indicated controller action will be run.

Pipelines are defined using the `pipeline` macro which describes a sequence of plugs to run on the connection. The `scope` macros define which pipelines to run using the `pipe_through` macro.

In this example, our GET request to `http://localhost:4000/` will match `get "/"` definition so the `PageController.index` function will be called after the `:browser` pipeline plugs are called with the connection. The `:browser` pipeline is called because the `get "/"` is defined inside a scope that specifies a pipeline using `pipe_through`.

The Phoenix Router is analogous to the `routes.rb` file in Ruby on Rails. The `mix phoenix.routes` command will list the routes and path helpers defined by the router.

{% highlight elixir %}
defmodule HelloWorld.Router do
  use HelloWorld.Web, :router

  pipeline :browser do
    plug :accepts, ["html"]
    plug :fetch_session
    plug :fetch_flash
    plug :protect_from_forgery
  end

  pipeline :api do
    plug :accepts, ["json"]
  end

  scope "/", HelloWorld do
    pipe_through :browser # Use the default browser stack

    get "/", PageController, :index
  end

  # Other scopes may use custom stacks.
  # scope "/api", HelloWorld do
  #   pipe_through :api
  # end
end
{% endhighlight %}

# Phoenix Controller
The controller is where application logic is done. Often this will include running SQL queries using the `Ecto` database library which is not covered in this article.

The params variable will contain a string keyed map of request parameters. Next, `Phoenix.Controller.render/2` is called with the `conn` and template name `index.html`. Often, `Phoenix.Controller.render/3` will be called with additional data to render like this: `render conn, "index.html", [data: "data"]`.

The `Phoenix.Controller.render/2` method will lookup the template file which by convention should be located in `web/templates/page/index.html.eex` and will then call the `Phoenix.View.render_to_iodata/3` function.

{% highlight elixir %}
defmodule HelloWorld.PageController do
  use HelloWorld.Web, :controller

  plug :action

  def index(conn, _params) do
    render conn, "index.html"
  end
end
{% endhighlight %}

# Phoenix View
Aside from rendering the template, the view also can provide helper functions and path helpers which will automatically be available to the template.

{% highlight elixir %}
defmodule HelloWorld.PageView do
  use HelloWorld.Web, :view
end
{% endhighlight %}

# Phoenix Template
By default, an html formatted EEx template was generated. EEx means Embedded Elixir which allows Elixir code to be included in template files.

The `index.html.eex` file that was generated only contains html by default. So, an alternative template example is shown here.
{% highlight erb %}
<div>
  <p><%= "This is Elixir code" %></p>
</div>
{% endhighlight %}

# HTTP Response
After the view renders the template, the controller will then call the Plug `send_resp` method with the rendered template data to return the HTTP response.

The user receives the rendered template in the browser.

# Links
- [Phoenix Framework](http://www.phoenixframework.org/)
- [Plug](https://hexdocs.pm/plug/readme.html)
- [Cowboy](http://ninenines.eu/)
- [Ecto](https://hexdocs.pm/ecto/Ecto.html)
