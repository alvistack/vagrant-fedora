# Vagrant Box Packaging for Fedora

[![GitLab pipeline
status](https://img.shields.io/gitlab/pipeline/alvistack/vagrant-fedora/master)](https://gitlab.com/alvistack/vagrant-fedora/-/pipelines)
[![GitHub
release](https://img.shields.io/github/release/alvistack/vagrant-fedora.svg)](https://github.com/alvistack/vagrant-fedora/releases)
[![GitHub
license](https://img.shields.io/github/license/alvistack/vagrant-fedora.svg)](https://github.com/alvistack/vagrant-fedora/blob/master/LICENSE)
[![Vagrant Box
download](https://img.shields.io/badge/dynamic/json?label=alvistack%2Ffedora-33&query=%24.boxes%5B%3A1%5D.downloads&url=https%3A%2F%2Fapp.vagrantup.com%2Fapi%2Fv1%2Fsearch%3Fq%3Dalvistack%2Ffedora-33)](https://app.vagrantup.com/alvistack/boxes/fedora-33)

Fedora is a Linux distribution developed by the community-supported
Fedora Project which is sponsored primarily by Red Hat, a subsidiary of
IBM, with additional support from other companies. Fedora contains
software distributed under various free and open-source licenses and
aims to be on the leading edge of free technologies. Fedora is the
upstream source of the commercial Red Hat Enterprise Linux distribution,
and subsequently CentOS as well.

Learn more about Fedora: <https://getfedora.org/>

## Supported Boxes and Respective Packer Template Links

  - [`alvistack/fedora-33`](https://app.vagrantup.com/alvistack/boxes/fedora-33)
      - [`packer/libvirt-33/packer.json`](https://github.com/alvistack/vagrant-fedora/blob/master/packer/libvirt-33/packer.json)
      - [`packer/virtualbox-33/packer.json`](https://github.com/alvistack/vagrant-fedora/blob/master/packer/virtualbox-33/packer.json)

## Overview

  - Packaging with [Packer](https://www.packer.io/)
  - Minimal [Vagrant base box
    implementation](https://www.vagrantup.com/docs/boxes/base)
  - Support [QEMU Guest
    Agent](https://wiki.qemu.org/Features/GuestAgent)
  - Support [VirtualBox Guest
    Additions](https://www.virtualbox.org/manual/ch04.html)
  - Support [Vagrant synced folder with
    rsync](https://www.vagrantup.com/docs/synced-folders/rsync)
  - Support [Vagrant provisioner with
    Ansible](https://www.vagrantup.com/docs/provisioning/ansible)
  - Standardize disk partition with GPT
  - Standardize file system mount with UUID
  - Standardize network interface with `eth0`

### Quick Start

Once you have [Vagrant](https://www.vagrantup.com/docs/installation) and
[VirtaulBox](https://www.virtualbox.org/) installed, run the following
commands under your [project
directory](https://learn.hashicorp.com/tutorials/vagrant/getting-started-project-setup?in=vagrant/getting-started):

    # Initialize Vagrant
    vagrant init alvistack/fedora-33
    
    # Start the virtual machine
    vagrant up
    
    # SSH into this machine
    vagrant ssh
    
    # Terminate the virtual machine
    vagrant destroy --force

## Versioning

### `YYYYMMDD.Y.Z`

Release tags could be find from [GitHub
Release](https://github.com/alvistack/vagrant-fedora/releases) of this
repository. Thus using these tags will ensure you are running the most
up to date stable version of this image.

### `YYYYMMDD.0.0`

Version tags ended with `.0.0` are rolling release rebuild by [GitLab
pipeline](https://gitlab.com/alvistack/vagrant-fedora/-/pipelines) in
weekly basis. Thus using these tags will ensure you are running the
latest packages provided by the base image project.

## License

  - Code released under [Apache License 2.0](LICENSE)
  - Docs released under [CC BY
    4.0](http://creativecommons.org/licenses/by/4.0/)

## Author Information

  - Wong Hoi Sing Edison
      - <https://twitter.com/hswong3i>
      - <https://github.com/hswong3i>
