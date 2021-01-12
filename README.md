# Vagrant Box Packaging for Fedora

[![Gitlab pipeline status](https://img.shields.io/gitlab/pipeline/alvistack/vagrant-fedora/master)](https://gitlab.com/alvistack/vagrant-fedora/-/pipelines)
[![GitHub release](https://img.shields.io/github/release/alvistack/vagrant-fedora.svg)](https://github.com/alvistack/vagrant-fedora/releases)
[![GitHub license](https://img.shields.io/github/license/alvistack/vagrant-fedora.svg)](https://github.com/alvistack/vagrant-fedora/blob/master/LICENSE)
[![Vagrant Box download](https://img.shields.io/vagrant/pulls/alvistack/fedora.svg)](https://hub.vagrant.com/r/alvistack/fedora/)

GitLab is a complete DevOps platform, delivered as a single application. This makes GitLab unique and makes Concurrent DevOps possible, unlocking your organization from the constraints of a pieced together toolchain. Join us for a live Q\&A to learn how GitLab can give you unmatched visibility and higher levels of efficiency in a single application across the DevOps lifecycle.

Learn more about GitLab: <https://about.gitlab.com/>

## Supported Boxes and Respective Packer Template Links

  - [`alvistack/fedora-13.7`](https://app.vagrantup.com/alvistack/boxes/fedora-13.7)
      - [`libvirt`](https://github.com/alvistack/vagrant-fedora/blob/master/packer/libvirt-13.7/packer.json)
      - [`virtualbox`](https://github.com/alvistack/vagrant-fedora/blob/master/packer/virtualbox-13.7/packer.json)
  - [`alvistack/fedora-13.6`](https://app.vagrantup.com/alvistack/boxes/fedora-13.6)
      - [`libvirt`](https://github.com/alvistack/vagrant-fedora/blob/master/packer/libvirt-13.6/packer.json)
      - [`virtualbox`](https://github.com/alvistack/vagrant-fedora/blob/master/packer/virtualbox-13.6/packer.json)

## Overview

This Docker container makes it easy to get an instance of Fedora up and running.

Based on [Official Fedora Docker Image](https://hub.docker.com/_/fedora/) with some minor hack:

  - Packaging by Packer Docker builder and Ansible provisioner in single layer
  - Handle `ENTRYPOINT` with [catatonit](https://github.com/Fedora/catatonit)

### Quick Start

For the `VOLUME` directory that is used to store the repository data (amongst other things) we recommend mounting a host directory as a [data volume](https://docs.docker.com/engine/tutorials/dockervolumes/#/data-volumes), or via a named volume if using a docker version \>= 1.9.

Start Fedora:

    # Pull latest image
    docker pull alvistack/fedora
    
    # Run as detach
    docker run \
        -itd \
        --name fedora \
        --volume /etc/fedora:/etc/fedora \
        --volume /var/run/docker.sock:/var/run/docker.sock \
        alvistack/fedora

**Success**. Fedora is now available.

## Upgrade

To upgrade to a more recent version of Fedora you can simply stop the Fedora
container and start a new one based on a more recent image:

    docker stop fedora
    docker rm fedora
    docker run ... (see above)

As your data is stored in the data volume directory on the host, it will still
be available after the upgrade.

Note: Please make sure that you don't accidentally remove the fedora container and its volumes using the -v option.

## Backup

For evaluations you can use the built-in database that will store its files in the Fedora home directory. In that case it is sufficient to create a backup archive of the directory on the host that is used as a volume (`/var/opt/gitlab` in the example above).

## Versioning

### `alvistack/fedora:latest`

The `latest` tag matches the most recent [GitHub Release](https://github.com/alvistack/vagrant-fedora/releases) of this repository. Thus using `alvistack/fedora:latest` or `alvistack/fedora` will ensure you are running the most up to date stable version of this image.

### `alvistack/fedora:<version>`

The version tags are rolling release rebuild by [Travis](https://travis-ci.com/alvistack/vagrant-fedora) in weekly basis. Thus using these tags will ensure you are running the latest packages provided by the base image project.

## License

  - Code released under [Apache License 2.0](LICENSE)
  - Docs released under [CC BY 4.0](http://creativecommons.org/licenses/by/4.0/)

## Author Information

  - Wong Hoi Sing Edison
      - <https://twitter.com/hswong3i>
      - <https://github.com/hswong3i>
