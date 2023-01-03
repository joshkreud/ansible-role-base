# Ansibe role Base

This is Joshs Base Ansible role.
It's used to setup basic things on a server.\
It also installs UFW and Fail2Ban.
SSH Disallows Root Login and Password login

## Variables

See [defaults](defaults/main.yml)

### Optional Variables
```yml
# Example for Deploy Users
deploy_users: # List of Users that Should be deployed
  - name: joshua
    sudoers: "ALL=(ALL:ALL) NOPASSWD:ALL" # Optional
    groups:
    - "docker"
    pubkey: | # Multiline String
    ssh-ed25519 akdnqwpondqp.... ssh_keyname
```
