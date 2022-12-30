# Ansibe role Base

This is Joshs Base Ansible role.
It's used to setup basic things on a server.\
It also installs UFW and Fail2Ban.
SSH Disallows Root Login and Password login

## Usage

| Variable               | Effect                                                                               |
| ---------------------- | ------------------------------------------------------------------------------------ |
| `time_zone`            | Timezone to set on server (Optional see [defaults](defaults/main.yml) )              |
| `hostname`             | Hostname to set in Server (Optional)                                                 |
| `default_packages`     | Packages to install by default. (Optional see [defaults](defaults/main.yml) )        |
| `deploy_users`         | Dict of name/sudoers/groups/pubkey (Optional)                                        |
| `lockdown_allow_ports` | List of Dict port:proto to open in UFW  (Optional see [defaults](defaults/main.yml)) |
| `ssh_tcp_port`         | SSH port to limit using ufw  (Optional see [defaults](defaults/main.yml))            |

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
