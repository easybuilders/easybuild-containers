# easybuild-containers

Containers for testing EasyBuild, built automatically for `x86_64` and `aarch64`, and available via the
[GitHub Container Registry (`ghcr.io`)](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-container-registry).

## Available containers images


* `almalinux-8.10`: [recipe](https://github.com/easybuilders/easybuild-containers/blob/main/almalinux-8.10/Dockerfile), [image @ ghcr.io](https://github.com/easybuilders/easybuild-containers/pkgs/container/almalinux-8.10)
* `almalinux-9.5`: [recipe](https://github.com/easybuilders/easybuild-containers/blob/main/almalinux-9.5/Dockerfile), [image @ ghcr.io](https://github.com/easybuilders/easybuild-containers/pkgs/container/almalinux-9.5)
* `centos-7.9`: [recipe](https://github.com/easybuilders/easybuild-containers/blob/main/centos-7.9/Dockerfile), [image @ ghcr.io](https://github.com/easybuilders/easybuild-containers/pkgs/container/centos-7.9)
* `centos-7.9-python3`: [recipe](https://github.com/easybuilders/easybuild-containers/blob/main/centos-7.9-python3/Dockerfile), [image @ ghcr.io](https://github.com/easybuilders/easybuild-containers/pkgs/container/centos-7.9-python3)
* `centos-8.5`: [recipe](https://github.com/easybuilders/easybuild-containers/blob/main/centos-8.5/Dockerfile), [image @ ghcr.io](https://github.com/easybuilders/easybuild-containers/pkgs/container/centos-8.5)
* `centosstream-9`: [recipe](https://github.com/easybuilders/easybuild-containers/blob/main/centosstream-9/Dockerfile), [image @ ghcr.io](https://github.com/easybuilders/easybuild-containers/pkgs/container/centosstream-9)
* `fedora-41`: [recipe](https://github.com/easybuilders/easybuild-containers/blob/main/fedora-41/Dockerfile), [image @ ghcr.io](https://github.com/easybuilders/easybuild-containers/pkgs/container/fedora-41)
* `opensuse-15.6`: [recipe](https://github.com/easybuilders/easybuild-containers/blob/main/opensuse-15.6/Dockerfile), [image @ ghcr.io](https://github.com/easybuilders/easybuild-containers/pkgs/container/opensuse-15.6)
* `rockylinux-8.10`: [recipe](https://github.com/easybuilders/easybuild-containers/blob/main/rockylinux-8.10/Dockerfile), [image @ ghcr.io](https://github.com/easybuilders/easybuild-containers/pkgs/container/rockylinux-8.10)
* `rockylinux-9.5`: [recipe](https://github.com/easybuilders/easybuild-containers/blob/main/rockylinux-9.5/Dockerfile), [image @ ghcr.io](https://github.com/easybuilders/easybuild-containers/pkgs/container/rockylinux-9.5)
* `ubuntu-20.04`: [recipe](https://github.com/easybuilders/easybuild-containers/blob/main/ubuntu-20.04/Dockerfile), [image @ ghcr.io](https://github.com/easybuilders/easybuild-containers/pkgs/container/ubuntu-20.04)
* `ubuntu-20.04-python36`: [recipe](https://github.com/easybuilders/easybuild-containers/blob/main/ubuntu-20.04-python36/Dockerfile), [image @ ghcr.io](https://github.com/easybuilders/easybuild-containers/pkgs/container/ubuntu-20.04-python36)
* `ubuntu-20.04-python2`: [recipe](https://github.com/easybuilders/easybuild-containers/blob/main/ubuntu-20.04-python2/Dockerfile), [image @ ghcr.io](https://github.com/easybuilders/easybuild-containers/pkgs/container/ubuntu-20.04-python2)
* `ubuntu-22.04`: [recipe](https://github.com/easybuilders/easybuild-containers/blob/main/ubuntu-22.04/Dockerfile), [image @ ghcr.io](https://github.com/easybuilders/easybuild-containers/pkgs/container/ubuntu-22.04)
* `ubuntu-24.04`: [recipe](https://github.com/easybuilders/easybuild-containers/blob/main/ubuntu-24.04/Dockerfile), [image @ ghcr.io](https://github.com/easybuilders/easybuild-containers/pkgs/container/ubuntu-24.04)

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
