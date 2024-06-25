# Containers

### Useful command to stop all containers

```
docker stop $(docker ps -a -q)
```

### Useful command to remove all containers

```
docker rm $(docker ps -a -q)
```

| Command | Description |
| --- | --- |
| `docker container` | Manage containers. |
| `docker container attach` | Attach local standard input, output, and error streams to a running container. |
| `docker container commit` | Create a new image from a container's changes. |
| `docker container create` | Create a new container. |
| `docker container diff` | Inspect changes to files or directories on a container's filesystem. |
| `docker container exec` | Execute a command in a running container. |
| `docker container export` | Export a container's filesystem as a tar archive. |
| `docker container inspect` | Display detailed information on one or more containers. |
| `docker container kill` | Force stop a running container. |
| `docker container logs` | Fetch the logs of a container. |
| `docker container ls` | List containers. |
| `docker container pause` | Pause all processes within a container. |
| `docker container port` | List port mappings or a specific mapping for the container. |
| `docker container prune` | Remove all stopped containers. |
| `docker container rename` | Rename a container. |
| `docker container restart` | Restart one or more containers. |
| `docker container rm` | Remove one or more containers. |
| `docker container run` | Run a command in a new container. |
| `docker container start` | Start one or more stopped containers. |
| `docker container stats` | Display a live stream of container(s) resource usage statistics. |
| `docker container stop` | Stop one or more running containers. |
| `docker container top` | Display the running processes of a container. |
| `docker container unpause` | Unpause all processes within a container. |
| `docker container update` | Update resource configs of one or more containers. |
| `docker container wait` | Block until a container stops, then print its exit code. |
| `docker container prune` | Remove all stopped containers. |
