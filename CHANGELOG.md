# Changelog

## 0.1 series

### 0.1.23 (2014-03-24)

- Hadoop and Cassandra clients make symlinks to `hadoop`, `cql`, etc commands
- Specify Python logging configuration file using `-l` when starting server
- Remove ghosted Mongo instances when starting
- Update documentation to reflect upgrades
- Fix specifying `-u` and `-k` at same time when installing

### 0.1.24 (2014-03-28)

- Images now mount the key directory instead of being hard-coded
- Dockerfiles no longer need privileged to build
- Images are now tagged with version
- Images are now hosted on Docker public index
- YAML support

### 0.1.26 (2014-04-05)

- Skipped version 0.1.25 due to packaging error
- Stop/restart storage services without losing data
- Use custom Dockerfile images for connectors
- Connectors get random names unless supplied with user-defined name

### 0.1.27 (2014-04-18)

- Port forwarding
- Fix issues restarting GlusterFS/Yarn stacks

### 0.1.28 (2014-04-25)

- Vagrant support
- Check LXC version during install
