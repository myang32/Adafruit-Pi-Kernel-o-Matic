# Raspberry Pi Kernel-o-Matic

![kernel-o-matic](/docs/pngn_kernelomatic_with_logos.gif?raw=true)

## Compiling The Raspberry Pi Kernel

Clone the git repo & start the vagrant box:

```
$ git clone git@github.com:adafruit/Pi_vagrant.git
$ cd Pi_vagrant
$ vagrant up
```

Once the vagrant box is up, SSH in:

```
$ vagrant ssh
```

Now that you are connected to the VM, check out the help for a list of options:

```
~$ sudo adabuild -h
usage: adabuild [options]
 This will build the Raspberry Pi Kernel.
 OPTIONS:
    -h        Show this message
    -r        The remote git repo to clone
              Default: https://github.com/raspberrypi/linux
    -b        The git branch to use
              Default: Default git branch of repo
    -1        The config file to use when compiling for Raspi v1
              Default: arch/arm/configs/bcmrpi_defconfig
    -2        The config file to use when compiling for Raspi v2
              Default: arch/arm/configs/bcm2709_defconfig
```

Compile with default options:

```
~$ sudo adabuild
```

Compile [adafruit-raspberrypi-linux][1] using the `rpi-3.15.y` branch:

```
~$ sudo adabuild -r https://github.com/adafruit/adafruit-raspberrypi-linux -b rpi-3.15.y
```

Compile for Docker

```
sudo adabuild -1 /vagrant/v1_docker -2 /vagrant/v2_docker
```
[1]: https://github.com/adafruit/adafruit-raspberrypi-linux
