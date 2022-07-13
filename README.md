# Ansible Playbooks

## Technologies

- Ansible 2.12.1

## Installation

#### Note: My operating system is archlinux 

```sh
pacman -Sy
```

```sh
pacman -S ansible
```

## Example Inventory File

- Create fileHosts and add the following:

```sh
[example]
IpAddress or domain
[example:vars]
ansible_ssh_user=userLinux
ansible_ssh_private_key_file=/path/keySshFile
ansible_ssh_port=22
```

## Ansible ping

```sh
ansible all -i fileHosts -m ping
``` 

## Contributions

- [Owen-Wilson](https://github.com/owenwilson)
