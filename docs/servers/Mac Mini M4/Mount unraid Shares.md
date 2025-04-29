# On unraid
Set the NFS Share to export `Yes`.

# On MacOS


1. macOS uses the Automounter (automount/autofs) rather than a Linux‐style /etc/fstab. 
```bash
sudo nano /etc/auto_master
```

and add the following line to the end of the file:

```bash
/-    auto_nfs    -nobrowse,nosuid
```

2. Create and edit /etc/auto_nfs:
```bash
sudo nano /etc/auto_nfs
```

and add the line:
```bash
/Volumes/<shareName>  -fstype=nfs,rw,nfsvers=3,hard,intr    <IP of unraid>:</path/to/share>
```

so it looks like this:
```bash
/Volumes/media  -fstype=nfs,rw,nfsvers=3,hard,intr    <IP of unraid>:/mnt/user/media
```

3. Reload the automounter
```bash
sudo automount -vc
```