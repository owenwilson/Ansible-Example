# Raspbian Roles
necesita actualizar la cache y limpiarla use lo siguiente:

sh'''
ansible-playbook -i inventory site.yml -t raspberry -e 'update_cache=true'
'''

necesita actualizar el sistema operativo de raspbian use lo siguiente:

sh'''
ansible-playbook -i inventory site.yml -t raspberry -e 'upgrade_system=true'
'''

necesita instalar open jdk 8 use lo siguiente:

sh'''
ansible-playbook -i inventory site.yml -t raspberry -e 'openjdk8=true'
'''

necesita instalar nginx use lo siguiente:

sh'''
ansible-playbook -i inventory site.yml -t raspberry -e 'nginx=true'
'''