# Ansible Playbooks

## Technologies

- Ansible 2.12.1

## Install Ansible on distrubution linux

#### archlinux 

```sh
pacman -Sy
```

```sh
pacman -S ansible
```

#### fedora

```sh
sudo dnf update -y
```

```sh
sudo dnf install ansible
```

```sh
ansible --version
```

## ssh
- standard [ssh ed25519](https://datatracker.ietf.org/doc/rfc8709/)

```sh
ssh-keygen -t ed25519
```

```sh
ssh-copy-id -i /home/user/.ssh/key_ssh.pub user@IPAddress
```

- check your the list of authorized keys on your remote server

```sh
cat /home/user/.ssh/authorized_keys
```

## Example Inventory File

- Create fileHosts and add the following:


```sh
touch invetory
```

or

```sh
touch hosts
```

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
