# playbook docker

## example ansible installation
- install docker
```sh
ansible-playbook site.yml -i hosts -t docker
```

- uninstall old docker version
```sh
ansible-playbook site.yml -i hosts -t docker -e uninstall=true
```
