## Prerequisite
Ansible master host should have passwordless access to target hosts, preferably to root user otherwise update remote_user parameter accordingly.

## Add user to target hosts and grant SSH access
ansible-playbook -i inventory/ -e "action=grant" playbooks/ssh.yml

## Revoke SSH access from target hosts (don't delete the user)
ansible-playbook -i inventory/ -e "action=revoke" playbooks/ssh.yml

## Remove user, it will revoke SSH access as well
ansible-playbook -i inventory/ -e "action=remove_user" playbooks/ssh.yml

