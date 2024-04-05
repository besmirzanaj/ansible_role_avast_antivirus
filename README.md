# ansible_role_avast_antivirus

This role is to install the Avast Antivirus for Linux. 

Official ocumentation for Avast Antivirus for Linux is located here - https://repo.avcdn.net/linux-av/doc/avast-techdoc.pdf


## Requirements

### OS

A Debian or RHEL family systemd based Linux system.

### License file

On a linux host (it could be your ansible control node) create a license file under `files` with the steps below (make sure to install avast-license package):

```console
$ avastlic -v -o ./license.avastlic -c <YOUR-LICENSE-OR-WALLET-KEY>
```

Copy the newly generated `license.avastlic` file into the `files` directory of this role. If you're storing the license file somewhere else, update the `avast_license_file` var accordingly with the new path.

## Role Variables

Generic OS variables are defined in the `vars` dir.

Custom role variables:

- `avast_license_file` - The location of the Avast license file. 


## Dependencies

NA

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
