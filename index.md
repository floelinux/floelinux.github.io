## Floe

Floe is a lightweight Linux distribution made specifically to run Linux containers.

It uses [Tiny Core Linux](http://tinycorelinux.net/), runs completely from RAM and is a ~16 MB download*.

### Supported Runtimes

#### Docker

Version 20.10 and later

See [boot2docker](https://github.com/boot2docker/boot2docker) for 19.03

#### Podman

Version 2.1.0 and later

See [boot2podman](https://github.com/boot2podman/boot2podman) for 1.9.3

### Version History

Version | TCL     | Kernel | Glibc  | Status
------- | ------- | ------ | ------ | ------
0.x     | 10.x    | 4.19   | 2.28   | Previous
1.x     | 11.x    | 5.4    | 2.30   | Current
2.x     | 12.x    | 5.10   | 2.32   | Alpha

----

\* _for the boot image, excluding packages_

Based on the original [CorePure64 ISO](http://tinycorelinux.net/10.x/x86_64/archive/10.0/CorePure64-10.0.iso)
