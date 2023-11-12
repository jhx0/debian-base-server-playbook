# debian-base-server-playbook
This Playbook sets up a Debian server system with sane defaults and some extras that are useful on a fresh Debian install.   
(This Playbook is geared towards a server install - but can be used for desktop systems to of course)

Tested on Debian 12 (Bookwork)

## Before running the Playbook:
- Configure **vars/main.yml** to your need.
- Make sure to edit the variable **ssh_keys** so that your public key is copied to the target system.
- In general: Select what you need from the playbook.

## Usage:
1. Clone/download this repository
2. Unpack/cd into the directory
3. Run
```Shell
$ ansible-playbook main.yml (-Kk)
```
4. Done

## Examples
All tasks can be selected via **Tags**, so you can pick whatever tasks you want to run.   
Following, a couple of use cases:
1. Run all tasks
```Ansible
$ ansible-playbook main.yml --tags all (-Kk)
```
2. Only run a subset of tasks
```Ansible
ansible-playbook main.yml --tags "apt,postfix,sudo,fail2ban,docker" (-Kk)
```
3. Run only one task
```
ansible-playbook main.yml --tags "packages" (-Kk)
```
All available **Tags**:
```Shell
apt
upgrade
postfix
ntp
sshd
sudo
sysctl
grub
home_fix
fail2ban
packages
groups
logwatch
ssh_key
qemu_guest
docker
aide
```

## Note:
Make sure you have set the correct IP/Hostname in the **hosts** file.   

**BEWARE:** do **_NOT_** run this Playbook blindly!
