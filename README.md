# debian-base-server-playbook
This Playbook sets up a Debian server system with sane defaults and some extras that are useful on a fresh Debian install.

## Before running the Playbook:
- Configure **group_vars/all** to your need.
- Make sure to edit the role **ssh_keys** so that your public key is copied to the target system.
- There are two firewall roles defined: **ufw** / **nftables**. Chose the one you like, or none. (Edit **site.yml**)
- In general: Select from **site.yml** what you need and comment out roles you don't want to run.

## Usage:
1. Clone/download this repository
2. Unpack/cd into the directory
3. Run
```
$ ansible-playbook -i hosts site.yml -Kk
```
4. The target will reboot when the playbook is finished running
5. Done

## Note:
Make sure you have set the correct IP/Hostname in the **hosts** file.   
Take a look at the provided roles in the **site.yml** file!

**BEWARE:** do **_NOT_** run this Playbook blindly!
