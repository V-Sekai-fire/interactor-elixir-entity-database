# interactor-elixir-entity-database

An Elixir prototype that receives fixed-size entity states over UDP and passes them through a dataflow pipeline that hashes and orders them.

## What it is for

It explores a world server that collects every player's state each tick. Pipeline filters hash each incoming state and arrange states in a left-child, right-sibling tree, and a small engine client script in `client/` sends test states. `design.md` holds the notes it started from.

## Build and run

```sh
mix deps.get
mix test
```

The numeric backend needs a native tensor library, and `HACKING.md` notes its setup.

## Licence

MIT; see LICENSE.
