# interactor-elixir-entity-database

An Elixir prototype that receives entity states over UDP and passes them through a dataflow pipeline that hashes them.

## What it is for

It explores a world server that collects every player's state each tick. The pipeline hashes each incoming UDP payload. A filter that arranges states in a left-child, right-sibling tree exists but is not wired into the pipeline. A small engine client script in `client/` sends test states. `design.md` holds the notes it started from.

## Build and run

```sh
mix deps.get
mix test
```

The numeric backend needs a native tensor library, and `HACKING.md` notes its setup. The filters use the dataflow library's pre-1.0 callbacks while `mix.exs` pins 1.0, so the filters do not run inside the pipeline as written; the tests call the filter functions directly.

## Licence

MIT; see LICENSE.
