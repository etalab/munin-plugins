# munin-plugins
A collection of plugins for Munin used @Etalab.

- [MongoDB](mongo/)
- [Redis](redis/)
- [udata](udata/)

## udata-worker-status

Plugin to graph the number of Celery tasks by type currently in the Celery queue. Relies on the `udata worker status` command of uData.

