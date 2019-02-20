# Munin plugins for MongoDB

Monitor MongoDB using Munin

## Requirements

* MongoDB 3+
* Python 2.7+
* Pymongo

## Common parameters

These plugins rely on environment variables for configuration.

They share the `MONGO_URI` parameter which default to localhost if not provided.

If you want to graph an instance which is not available on `mongodb://localhost:27017`, you will need to provide this parameter into your plugin's configuration.

**Ex:** For a MongoDB instance running on `any.host:27018`, a `/etc/munin/plugin-conf.d/mongo` file can contain:

```ini
[mongo_*]
env.MONGO_URI mongodb://any.host:27017
```

## Plugins

### `mongo_conn`

Display the number of current connections

### `mongo_db_`

A multigraph plugin providing the following metrics for a given database:
- average object size
- per collection data size
- per collection document count
- per collection index size
- per collection storage size

#### Parameters

* `MONGO_IGNORE_COLLECTION`: a comma separated list of collections to ignore

#### Usage

This is a wildcard plugin expecting the database name as filename parameter.

**Ex:** to display metrics about `mine` collection, just name it `mongo_db_mine`

```shell
ln -s /path/to/repository/mongo/mongo_db_ /etc/munin/plugins/mongo_db_mine
```

### `mongo_mem`

Graph MongoDB mapped, virtual and resident memory usage

### `mongo_ops`

Graph the number of operations by second
