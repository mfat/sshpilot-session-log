# Session Log (sshPilot plugin)

Track when you open and close terminal sessions for each saved connection.
View a lightweight history, see per-host totals, and export CSV for billing or
incident timelines.

## Requirements

- sshPilot with plugin **API ≥ 1.4** (provides `ctx.list_connections()` for
  display context).

## Install

Copy this directory to your user plugin dir and enable it in
**Preferences ▸ Plugins** (then restart sshPilot):

- Linux: `~/.local/share/sshpilot/plugins/session-log/`
- Flatpak: `~/.var/app/io.github.mfat.sshpilot/data/sshpilot/plugins/session-log/`

Or install the released `.zip` from **Preferences ▸ Plugins ▸ Install plugin…**.

## Permissions

`connections`, `ui`, `settings` — declared for transparency; sshPilot plugins
run unsandboxed with full app privileges. Only install plugins you trust.

## Develop / test

```sh
pip install pytest "sshpilot @ git+https://github.com/mfat/sshpilot" --no-deps
pytest -ra
```

The session store (`SessionLogStore`) is pure Python and unit-tested without
GTK; `gi` is imported lazily inside the page factory.
