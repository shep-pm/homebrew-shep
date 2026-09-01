# homebrew-shep

The Homebrew tap for [shep](https://github.com/shep-pm/shep), a process manager
that keeps a flock of long-running processes alive.

```bash
brew install shep-pm/shep/shep
```

The formula builds from source, so the first install compiles the whole Rust
tree. Expect minutes rather than seconds. It installs all three binaries
`cargo install shep` would: `shep`, `shep-runtime` and `shep-dev`.

## This repository is generated

`Formula/shep.rb` is pushed here by shep's release workflow on every release.
Its source of truth is `packaging/homebrew/shep.rb` in the main repository, so
open pull requests against
[shep-pm/shep](https://github.com/shep-pm/shep) instead of against this
repository. Anything committed here directly is overwritten by the next
release.

## No brew services

shep installs its own launchd job through `shep startup`, and undoes it with
`shep unstartup`. The formula therefore ships no `brew services` definition:
running both would leave two launchd jobs pointed at one shepherd.

## License

MIT or Apache-2.0, at your option, matching shep itself.
