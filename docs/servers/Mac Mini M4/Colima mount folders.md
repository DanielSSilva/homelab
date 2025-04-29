By default, Colima only mounts $HOME and /tmp/colima are mounted as writable.
This means that, if you specify absolute paths on your docker compose, docker will not see them.

# Changes
Go to `$HOME/.colima/default/colima.yaml` and search for the `mounts` key. Edit to include your volumes
```yaml
mounts:
  - location: /Users/asgard
    writable: true
  - location: /tmp/colima
    writable: true
  - location: /Volumes/media
    writable: true
```