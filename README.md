# Docker volume nfs mounter

An example of the [Docker volume extension api](https://github.com/calavera/docker-volume-api)

Docker volume extension that NFS mounts a remote FS into your container

## Usage

`make build` to build the container

`make run` to run the volume plugin in a container, listening to the socket in the default
`/usr/share/docker/plugins/` dir.

To mount an NFS export `nfs://127.0.0.1:/data`, run:

        docker run --rm -it --volume-driver=nfs -v 127.0.0.1/data:/no busybox ls -la


To mount a device under dev, eg `/dev/sdc`, run:

        docker run --rm -it --volume-driver=nfs -v dev/sdc:/no busybox ls -la /no

> Note: because of the way docker parses colons, you need to omit them from the NFS share.

## License

MIT
