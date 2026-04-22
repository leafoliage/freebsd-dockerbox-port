# FreeBSD Dockerbox Port

This is the FreeBSD Port repository for [FreeBSD-Dockerbox](https://github.com/leafoliage/freebsd-dockerbox).

## Quickstart

### Install from port

> This port hasn't been added to official FreeBSD ports yet. Please copy port files or mount directory into `/usr/ports` first.

Null mount `sysutils/dockerbox` to `/usr/ports/sysutils/dockerbox`.

```sh
mkdir /usr/ports/sysutils/dockerbox
mount_nullfs sysutils/dockerbox /usr/ports/sysutils/dockerbox
```

Make under `/usr/ports/sysutils/dockerbox`

```sh
make install
```

Install helper packages.

```sh
pkg install grub2-bhyve e2fsprogs docker
```

> There is a recent patch for `grub2-bhve` essential to dockerbox. Please make sure the "latest" package repository is used instead of quarterly. Check with `pkg -vv`. Otherwise, `grub2-bhyve` should be built from port.

Enable and start the dockerbox service.

```sh
sysrc dockerbox_enable=YES
service dockerbox enable
service dockerbox start
```

Run docker command with remote docker specified.

```sh
docker -H 10.0.0.1:2375 run hello-world
```

### Install from source

See [freebsd-dockerbox Quickstart](https://github.com/leafoliage/freebsd-dockerbox#quickstart).
