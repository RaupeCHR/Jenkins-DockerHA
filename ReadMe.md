Launch a EC2 t2.micro Ubuntu 20.04 instance on AWS.
Connect via ssh.

sudo apt update

sudo apt install ansible

mkdir ansible_jenkins && cd ansible_jenkins
vi ansible.cfg

ansible-galaxy install geerlingguy.java
ansible-galaxy install geerlingguy.jenkins


Launch a EC2 t2.small Ubuntu 20.04 instance on AWS.


ansible-playbook playbooks/jenkins-playbook.yml

