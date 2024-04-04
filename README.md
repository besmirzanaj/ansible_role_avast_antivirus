# asible_role_avast_antivirus
=========

This role is to install the avast antivirus for Linux. 

Official ocumentation for Avast Antivirus for Linux is located here - https://repo.avcdn.net/linux-av/doc/avast-techdoc.pdf


## Requirements

### OS

A Debian or RHEL family systemd based Linux system.

### License file

On a linux host (it could be your ansible control node) create a license file under `files` with the steps below:

```console
$ avastlic -v -o ./license.avastlic -c <YOUR-LICENSE-OR-WALLET-KEY>
```

Copy the license.avastlic file into the `files` directory of this role and if this file is to be saved somewhere else, update the `avast_license_file` var accordingly with the new path.

## Role Variables

Generic OS variables are defined in the `vars` dir.

Custom role variables:

- avast_license_file - The location of the Avast license file. 


## Dependencies

na

## Example Playbook

```yaml

- hosts: servers
  become: yes
  roles:
    - ansible_role_avast_antivirus
```

## License

BSD

## Author Information

Besmir Zanaj
