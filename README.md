# Ansible Playbooks

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

## create ssh key
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

## example Inventory File

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

- configure multiple SSH keys in your hosts file or invetory file
```sh
[docker]
IP_address ansible_ssh_private_key_file=~/vbox/.vagrant/machines/node-1/virtualbox/private_key
IP_address ansible_ssh_private_key_file=~/vbox/.vagrant/machines/node-2/virtualbox/private_key
[docker:vars]
ansible_ssh_user=vagrant
#ansible_ssh_private_key_file=~/vbox/.vagrant/machines/node-1/virtualbox/private_key
ansible_ssh_port=22
```

## ansible ping

```sh
ansible all -i fileHosts -m ping
``` 

## example ansible installation
- install docker
```sh
ansible-playbook site.yml -i hosts -t docker
```

- uninstall old docker version
```sh
ansible-playbook site.yml -i hosts -t docker -e uninstall=true
```

- check [docker install documentation](https://docs.docker.com/engine/install/)
