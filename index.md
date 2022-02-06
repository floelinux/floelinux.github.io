---
title: Floe Linux
description: Lightweight Distribution
---

Floe is a lightweight Linux distribution made specifically to run Linux containers.

It uses [Tiny Core Linux](http://tinycorelinux.net/), runs completely from RAM and is a ~16 MB download*.

## Added Features

* Linux kernel configured with container support, like `cgroupfs` and `overlayfs`
* GNU C Library (glibc) made container friendly, to support old kernel versions
* Go language compiler package
* Container runtime packages

<img alt="Penguin on Ice Floe" src="/assets/floe.jpg" />

<a href="http://www.freepik.com">Designed by brgfx / Freepik</a>

## Supported Architectures

### amd64 (`x86_64`)

Also known as "**CorePure64**"

Core64 had a 64-bit kernel with 32-bit applications,
CorePure64 has 64-bit apps

![cdrom](assets/media-cdrom.png) `CorePure64.iso`

The default ISO bootloader is `isolinux`, and it is tuned for `generic` CPU (VM).

### arm64 (`aarch64`)

Also known as "**piCore64**"

piCore is the Raspberry Pi port of Tiny Core Linux,
piCore64 has 64-bit support

![cdrom](assets/media-flash.png) `piCore64.img`

This uses the SD card [bootloader](https://www.raspberrypi.org/documentation/hardware/raspberrypi/bootmodes/bootflow.md), and it is tuned for `cortex-a53` CPU (RPi3).

## Supported Runtimes

### Docker

Version 20.10 and later.
See [boot2docker](https://github.com/boot2docker/boot2docker) for 19.03

```console
$ tce-load -wi docker
```

Packages: runc.tcz, containerd.tcz, docker.tcz

### Podman

Version 2.1.0 and later.
See [boot2podman](https://github.com/boot2podman/boot2podman) for 1.9.3

```console
$ tce-load -wi podman
```

Packages: crun.tcz, conmon.tcz, podman.tcz

## Installation

There is currently no public release avaiable.

### Ice Machine

Virtual machines with Floe can be created using Ice, like so: `ice-machine create`.

Note: `ice-machine` is based on the previous `docker-machine` and `podman-machine`.

* [docker-machine](https://github.com/docker/machine) - creating machines with boot2docker.iso

* [podman-machine](https://github.com/boot2podman/machine) - creating machines with boot2podman.iso

### Raspberry Pi

The image download can be flashed directly, using [Balena Etcher](https://balena.io/etcher/) or similar SD tool.

## Packages

* compiletc.tcz
* go.tcz*
* git.tcz
* openssh.tcz
* docker.tcz*
* podman.tcz*

Repository, see: <https://cloudsmith.io/~floelinux/repos/>

Package repository hosting is graciously provided by [Cloudsmith](https://cloudsmith.com).

## Version History

TCL     | Kernel | Glibc  | Year   | Status
------- | ------ | ------ | ------ | ------
~~8.x~~ | 4.8    | 2.24   | 2017   | Obsolete
~~9.x~~ | 4.14   | 2.26   | 2018   | Obsolete
10.x    | 4.19   | 2.28   | 2019   | Previous
11.x    | 5.4    | 2.30   | 2020   | Previous
12.x    | 5.10   | 2.32   | 2021   | Current
13.x    | 5.15   | 2.34   | 2022   | Current

----

Based on the original [CorePure64 ISO](http://tinycorelinux.net/10.x/x86_64/archive/10.0/CorePure64-10.0.iso) and `tatsushid/tinycore:10.0-x86_64`.

See <https://github.com/tatsushid/docker-tinycore> for the original Dockerfile source

`kvm -cdrom CorePure64-10.0.iso`

![Screenshot of QEMU Core](/assets/qemu-core.png)

`docker images tatsushid/tinycore`

```text
REPOSITORY          TAG          IMAGE ID      CREATED        SIZE
tatsushid/tinycore  10.0-x86_64  939e756a8d71  23 months ago  8.65MB
```

```text
$ docker run -it docker.io/tatsushid/tinycore:10.0-x86_64
/ $
```

\* _for the boot image, excluding packages_

`15M	CorePure64-10.0.iso`<br />
`16M	CorePure64-11.0.iso`<br />
`17M	CorePure64-12.0.iso`<br />
`18M	CorePure64-13.0.iso`<br />

piCore 11.x only supported `arm32` (32-bit).

`24M	piCore64-12.0.zip`
