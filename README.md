# vagrant-bionic-docker - A Vagrant configuration for a sane docker server

There's several reasons to run Docker in a VM on a mac - the one I run into occasionally is networking. In some instances I want to run a container, and allow other hosts on my local network to access that service. This is outside the scope of what Docker thinks Docker for Mac should do, so instead of wrestling it into compliance, I just type `vagrant up`.

This is based on install notes at https://docs.docker.com/engine/install/ubuntu/.

## Shared folder
This configuration uses the directory the `Vagrantfile` is in as a shared folder in the VM, mounted at `/vagrant`. This allows an easy way to copy files into the VM, and have persistent data across VM lifecycles.

## Requirements:

* MacOS (this may work on linux, but I haven't tested)
* [vagrant](https://www.vagrantup.com/)
* [Virtualbox](https://www.virtualbox.org/) (the vagrant box I'm using isn't available for Parallels)

