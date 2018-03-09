# flame-install-playbooks

This repo contains ansible playbooks that I use to speedup installations, updates and uniformisation of autodesk flame workstations.

## Contents

### flamefetcher_18_3.yml

This playbook untars the DKU as well as the flame/flare/flameassist installer (depending on the ansible inventory hostname) from a CIFS share.

It can be used for installation as well as version upgrades, and can be modified to account for newer versions (this one is for version 2018.3). 

### flame_prep.yml

This playbook is supposed to be used just after a few things that I prefer to keep manual :
- DKU Install
- Storage setup
- Flame/flare/flameassist install, setup and test
- AJA Kona 4 fw update
- AD join (just the realm join {domain} command)

It sets up :

- sssd configuration just after AD join
- Default session skeleton (with app icons depending on host's inventory hostname)
- Custon kdmrc with company's logo
- Autofs setup
- Addition of a sudoers group (located in AD)
- Updating bashrc and profile to change umask
- Installing zabbix-agent
- Installing htop
- Installing fusion-inventory

If you need any of the templates I use, contact me directly.
