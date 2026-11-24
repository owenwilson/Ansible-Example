# Ansible Playbooks

## Install Ansible on distrubution linux

## ansible version

- Ansible 2.12.1

## install Ansible on distrubution linux

### archlinux 

```sh
pacman -Sy
```

```sh
pacman -S ansible
```

### fedora

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

### ssh

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
ansible_ssh_port=22
```

## ansible ping

=======
## ansible
 
### example ansible ping hosts
 
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

### example install aws-cli

- use the `-K` flag to ask your username's passwords 

```sh
ansible-playbook site.yml -i hosts -t aws -K
```

- uninstall aws-cli v2

```sh
ansible-playbook site.yml -i hosts -t aws -e uninstall=true -K
```

## references

- check out [install aws-cli](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
- check out [docker install documentation](https://docs.docker.com/engine/install/)

