## Netshare NFS Storage

### Changelog - 0.1.0

- Initial version of a storage template for rancher based on a containerized version of the Netshare Docker Volume plugin
- Mount any NFS share per container with a simple syntax. See [http://netshare.containx.io/docs/nfs] for examples.

#### Rancher NFS [johannrichard/netshare-storage:v0.34]

### Default Configuration

The configuration questions below will apply to all volumes by default.

Each volume manifests as a uniquely-named subfolder within the NFS server's export directory. Example:

```yaml
version: '2'
services:
  foo:
    image: alpine
    stdin_open: true
    volumes:
    - nfs-host/mount:/data
volumes:
  nfs-host/mount:
    driver: nfs
```