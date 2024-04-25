# Run Docker commands without sudo

### Verify if the `docker` group exists

```
$ sudo getent group docker
```

### If it doesn't exist, add it:

```
$ sudo groupadd docker
```

### Add the connected user `$USER` to the docker group

- Optionally change the username to match your preferred user.

```
$ sudo gpasswd -a $USER docker
```

### Log out and log back in so that your group membership is re-evaluated.

### Restart the `docker` daemon

#### If you are on systemd

```
$ sudo systemctl restart docker
```
