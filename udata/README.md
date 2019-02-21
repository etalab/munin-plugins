# Munin plugins for udata

Monitor udata using Munin

## Requirements

* udata

## Common parameters

These plugins rely on environment variables for configuration:
- `UDATA_BIN`: the full path to the udata binary.
- `UDATA_SETTINGS`: the full path to the `udata.cfg` settings file.

**Ex:** For a udata instance installed in `/srv/udata`, a `/etc/munin/plugin-conf.d/udata` file can contain:

```ini
[udata*]
env.UDATA_BIN /srv/udata/bin/udata
env.UDATA_SETTINGS /srv/udata/udata.cfg
```

## Plugins

### `udata-worker-status_`

Graphs the current number of Celery tasks by type in a given Celery queue.

Relies on the `udata worker status` command of udata.

#### Usage

This is a wildcard plugin expecting the queue name as filename parameter.

**Ex:** to display metrics about `default` queue, just name it `udata-worker-status_default`

```shell
ln -s /path/to/repository/udata/udata-worker-status_ /etc/munin/plugins/udata-worker-status_default
```
