## Floe

Floe is a lightweight Linux distribution made specifically to run Linux containers.

It uses [Tiny Core Linux](http://tinycorelinux.net/), runs completely from RAM and is a ~16 MB download*.

<img alt="Penguin on Ice Floe" src="/assets/floe.jpg" />

<a href="http://www.freepik.com">Designed by brgfx / Freepik</a>

### Supported Runtimes

#### Docker

Version 20.10 and later

* runc
* containerd
* docker

See [boot2docker](https://github.com/boot2docker/boot2docker) for 19.03

#### Podman

Version 2.1.0 and later

* crun
* conmon
* podman

See [boot2podman](https://github.com/boot2podman/boot2podman) for 1.9.3

### Version History

Version | TCL     | Kernel | Glibc  | Status
------- | ------- | ------ | ------ | ------
0.x     | 10.x    | 4.19   | 2.28   | Previous
1.x     | 11.x    | 5.4    | 2.30   | Current
2.x     | 12.x    | 5.10   | 2.32   | Alpha

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

\* _for the boot image, excluding packages_

`15M	CorePure64-10.0.iso`
