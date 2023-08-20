public:: true
tags:: Elixir

- Using [Mox](https://hexdocs.pm/mox/Mox.html) for #testing GenServers require (1) `setup :set_mox_global` and (2) `use ExUnit.Case, async: false`.
  This is due to expectations pinned to to pids by default. Doing so enables to be shared. Otherwise, if the relevant GenServer calls a mocked module/fun in a test, it would error out because it cannot use the expectations/stubs setup by the test process.