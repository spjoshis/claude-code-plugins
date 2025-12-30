---
name: phoenix-framework
description: Master Phoenix framework with LiveView, channels, contexts, Ecto, and real-time web applications with Elixir.
---

# Phoenix Framework

Build real-time web applications with Phoenix, LiveView, channels, and Elixir's concurrent architecture.

## Core Patterns

### LiveView
```elixir
defmodule MyAppWeb.UserLive.Index do
  use MyAppWeb, :live_view

  alias MyApp.Accounts

  def mount(_params, _session, socket) do
    {:ok, assign(socket, users: Accounts.list_users())}
  end

  def handle_event("delete", %{"id" => id}, socket) do
    user = Accounts.get_user!(id)
    {:ok, _} = Accounts.delete_user(user)

    {:noreply, assign(socket, users: Accounts.list_users())}
  end
end
```

### Controller
```elixir
defmodule MyAppWeb.UserController do
  use MyAppWeb, :controller

  alias MyApp.Accounts

  def index(conn, _params) do
    users = Accounts.list_users()
    render(conn, :index, users: users)
  end

  def create(conn, %{"user" => user_params}) do
    case Accounts.create_user(user_params) do
      {:ok, user} ->
        conn
        |> put_status(:created)
        |> render(:show, user: user)

      {:error, changeset} ->
        conn
        |> put_status(:unprocessable_entity)
        |> render(:error, changeset: changeset)
    end
  end
end
```

### Context
```elixir
defmodule MyApp.Accounts do
  alias MyApp.Accounts.User
  alias MyApp.Repo

  def list_users do
    Repo.all(User)
  end

  def create_user(attrs) do
    %User{}
    |> User.changeset(attrs)
    |> Repo.insert()
  end
end
```

## Best Practices

1. Use contexts for domain logic
2. Leverage LiveView for interactivity
3. Use Ecto changesets for validation
4. Implement proper error handling
5. Use channels for real-time features
6. Write ExUnit tests
7. Use telemetry for monitoring

## Resources
- https://phoenixframework.org
