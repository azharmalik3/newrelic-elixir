# NewRelic agent for Elixir

Based on https://github.com/wooga/newrelic-erlang and https://github.com/TheRealReal/new-relixir

## Installation

  1. Add `new_relic` to your list of dependencies in `mix.exs`:

    ```elixir
    def deps do
      [{:new_relic, github: "romul/newrelic.ex"}]
    end
    ```

  2. Ensure `new_relic` is started before your application:

    ```elixir
    def application do
      [applications: [:new_relic]]
    end
    ```

  3. Configure:

    ```elixir
    # config/config.exs

    config :new_relic,
      application_name: System.get_env("NEWRELIC_APP_NAME"),
      license_key: System.get_env("NEWRELIC_LICENSE_KEY"),
      poll_interval: 60_000 # push data to NewRelic once per 1 minute