# pihole

Attempt to build a Vagrant machine, configured using Ansible, to use Pi-hole, just not on a raspberry pi. The machine uses the "official" CentOS 7 box, 'centos/7' (https://app.vagrantup.com/centos/boxes/7). I'm using libvirt as my provider and my host is also CentOS 7 (not that it should matter, using these files). It disables SELinux, as the Pi-hole webinterface has problems with that and is therefor currently not supported. 

## Usage

Check **setupVars.conf.j2** to see if there's anything you don't like. Having this file present makes sure the installation script can run in *unattended* mode

Run
```
vagrant up
```

When the vagrant machine is installed, SSH into it.
```
vagrant ssh
```

Install Pi-hole (manually for now, but can easily be automated in the Ansible playbook. The MOTD will tell you how;

```
sudo bash basic-install.sh --unattended
```
## Troubleshooting

Right now, the installation of Pi-hole gives an error during installation, and I've created issue 2860 (https://github.com/pi-hole/pi-hole/issues/2860) for this.

This can be circumvented by adding the line BLOCKING_ENABLED to setupVars.conf.j2. Set it to either false, true, or whatever, and you'll be fine.
