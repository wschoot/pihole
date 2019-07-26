# pihole

Attempt to build a Vagrant machine, configured using Ansible, to use Pi-hole, just not on a raspberry pi.
The machine uses the "official" CentOS 7 box, 'centos/7' (https://app.vagrantup.com/centos/boxes/7)
I'm using libvirt as my provider and my host is also CentOS 7 (not that it should matter, using these files)
It disables SELinux, as the Pi-hole webinterface has problems with that and is therefor currently not supported

## Usage

Run
```
vagrant up
```

## Troubleshooting

Right now, the installation of Pi-hole gives an error during installation, and I've created issue 2860 (https://github.com/pi-hole/pi-hole/issues/2860) for this.
