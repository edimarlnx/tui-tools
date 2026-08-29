# tui-tools has moved to its own organization

**→ [github.com/tui-tools](https://github.com/tui-tools)**

This repository is archived. It was the monorepo the family started in; each
tool now lives in its own repository, with its own releases and its own issue
tracker.

| Was here | Is now |
| --- | --- |
| `cmd/fwall` | [**tui-firewall**](https://github.com/tui-tools/tui-firewall) — the system firewall |
| `pkg/theme`, `pkg/ui`, `internal/config` | [**tui-kit**](https://github.com/tui-tools/tui-kit) — the shared foundation |
| — | [**tui-systemd**](https://github.com/tui-tools/tui-systemd) — systemd units, journal, timers |
| — | [**tui-template**](https://github.com/tui-tools/tui-template) — a starting point for a new tool |

The git history came across: `tui-firewall` and `tui-kit` carry the commits
that produced the files they inherited, so `git log --follow` reaches back
through this repository's history.

## Why the split, and why the rename

One repository meant one release train and one issue tracker for tools that
have nothing to do with each other beyond looking alike. A firewall UI and a
systemd UI share a palette and a promise, not a version number.

`fwall` became `tui-firewall` at the same time. The family rule is now one name
per tool — `tui-<target>` for the repository, the Go module, the binary and the
config directory, with no aliases — and it was better to pay that cost at v0.1
than to leave one tool spelled differently from all the others.

Note that the configuration directory moved with the name: `/etc/fwall/` and
`~/.config/fwall/` are now `/etc/tui-firewall/` and `~/.config/tui-firewall/`.

## Installing

```sh
go install github.com/tui-tools/tui-firewall/cmd/tui-firewall@latest
```

Or download a static binary from the
[releases](https://github.com/tui-tools/tui-firewall/releases).

## The code below

Everything under this line is kept exactly as it was, for history. It is not
maintained, and the Go module path (`github.com/edimarlnx/tui-tools`) no longer
resolves to anything you should depend on.

## License

MIT — see [LICENSE](LICENSE).
