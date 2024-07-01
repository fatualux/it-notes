# Images

### Useful command to stop all images

```
docker stop $(docker ps -a -q)
```

### Useful command to remove all images

```
docker rmi $(docker images -q)
```

| Command | Description |
| --- | --- |
| `docker image` | Manage images. |
| `docker image build` | Build an image from a Dockerfile. |
| `docker image history` | Show the history of an image. |
| `docker image import` | Import the contents from a tarball to create a filesystem image. |
| `docker image inspect` | Display detailed information on one or more images. |
| `docker image load` | Load an image from a tar archive or STDIN. |
| `docker image prune` | Remove unused images. |
| `docker rmi` | Remove one or more images. |
| `docker image save` | Save one or more images to a tar archive (streamed to STDOUT by default). |
| `docker image tag` | Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE. |
| `docker image ls` | List images. |
| `docker pull` | Download an image from a registry. |
| `docker push` | Upload an image to a registry. |
