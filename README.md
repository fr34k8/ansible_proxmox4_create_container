# Proxmox 4 create container LXC by Ansible 

####Proxmox server
+ Install the `proxmoxer` module
```
pip install proxmoxer
```

####Ansible server
+ Install module extra
```
git@github.com:ansible/ansible-modules-extras.git
```

+ Export module path
```
export ANSIBLE_LIBRARY=/etc/ansible/ansible-modules-extras/cloud/misc/
```

Option 2: You can edit the `ansible.cfg` and setting the `library` var:

```
library        = /etc/ansible/ansible-modules-extras/cloud/misc/
```

+ Install the container
```
ansible-playbook --module-path=$ANSIBLE_LIBRARY crea_contenedores.yml -u root  
```

* Note: For new container you have add the new values in the `group_vars/proxmox` file


####From local PC
```
$ export PYTHONPATH=/Library/Python/2.7/site-packages/
$ export PROXMOX_ANSIBLE=$HOME/ansible/ansible-modules-extras/cloud/misc
$ ansible-playbook --module-path=$PROXMOX_ANSIBLE -i hosts crea_contenedores.yml -u root
```

Thanks: [Pbruna](https://gist.github.com/pbruna) 
