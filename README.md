# easybuild-containers

Containers for testing EasyBuild, built automatically for `x86_64` and `aarch64`, and available via the
[GitHub Container Registry (`ghcr.io`)](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-container-registry).

## Available containers images

* `centos-7.9`: [recipe](https://github.com/easybuilders/easybuild-containers/blob/main/centos-7.9/Dockerfile), [image @ ghcr.io](https://github.com/easybuilders/easybuild-containers/pkgs/container/centos-7.9)
* `centos-8.5`: [recipe](https://github.com/easybuilders/easybuild-containers/blob/main/centos-8.5/Dockerfile), [image @ ghcr.io](https://github.com/easybuilders/easybuild-containers/pkgs/container/centos-8.5)
* `centosstream-9`: [recipe](https://github.com/easybuilders/easybuild-containers/blob/main/centosstream-9/Dockerfile), [image @ ghcr.io](https://github.com/easybuilders/easybuild-containers/pkgs/container/centosstream-9)
* `fedora-35`: [recipe](https://github.com/easybuilders/easybuild-containers/blob/main/fedora-35/Dockerfile), [image @ ghcr.io](https://github.com/easybuilders/easybuild-containers/pkgs/container/fedora-35)
* `fedora-36`: [recipe](https://github.com/easybuilders/easybuild-containers/blob/main/fedora-36/Dockerfile), [image @ ghcr.io](https://github.com/easybuilders/easybuild-containers/pkgs/container/fedora-36)
* `opensuse-15.3`: [recipe](https://github.com/easybuilders/easybuild-containers/blob/main/opensuse-15.3/Dockerfile), [image @ ghcr.io](https://github.com/easybuilders/easybuild-containers/pkgs/container/opensuse-15.3)
* `rockylinux-8.5`: [recipe](https://github.com/easybuilders/easybuild-containers/blob/main/rockylinux-8.5/Dockerfile), [image @ ghcr.io](https://github.com/easybuilders/easybuild-containers/pkgs/container/rockylinux-8.5)
* `ubuntu-20.04`: [recipe](https://github.com/easybuilders/easybuild-containers/blob/main/ubuntu-20.04/Dockerfile), [image @ ghcr.io](https://github.com/easybuilders/easybuild-containers/pkgs/container/ubuntu-20.04)

## Usage with Singularity

To use these containers with Singularity:

* start shell in CentOS 7.9 container:
  ```
  singularity shell docker://ghcr.io/easybuilders/centos-7.9
  ```

* run commands in Ubuntu 20.04 container:
  ```
  singularity exec docker://ghcr.io/easybuilders/ubuntu-20.04 bash -c "cat /etc/debian_version; cat /etc/os-release"
  ```

## Build custom container images

You can build a custom container image on top of one of the provided container images.

For example, to build a CentOS 7.9 container that also includes the `openssl11*` packages using Singularity:

```
$ cat CentOS-7.9-openssl11.def
Bootstrap: docker
From: ghcr.io/easybuilders/centos-7.9
%post
    yum -y install openssl11 openssl11-devel

$ sudo singularity build CentOS-7.9-openssl11.sif CentOS-7.9-openssl11.def
```
