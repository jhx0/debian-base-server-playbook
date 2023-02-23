# debian-base-server-playbook
This Playbook sets up a Debian server system with sane defaults and some extras that are useful on a fresh Debian install.   
(This Playbook is geared towards a server install - but can be used for desktop system to of course)

## Before running the Playbook:
- Configure **vars/main.yml** to your need.
- Make sure to edit the variable **ssh_keys** so that your public key is copied to the target system.
- **ufw** will be used as a firewall. By default, port **22** (**SSH**) will be opened.
- In general: Select what you need from the playbook.

## Usage:
1. Clone/download this repository
2. Unpack/cd into the directory
3. Run
```Shell
$ ansible-playbook main.yml (-Kk)
```
4. Done

## Note:
Make sure you have set the correct IP/Hostname in the **hosts** file.   

**BEWARE:** do **_NOT_** run this Playbook blindly!
