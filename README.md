# ansible

## INVENTORY : Inventory is nothing but the list of machine ip or dns names that you want ansible to be managed

Ansible by default installs 2.9 as by default on AMI's we will get python2.
Always go with the latest verrsion,which can be installed from tools/ansible/install.sh

all is a group which includes all the entries in INVENTORY File

ANSIBLE has a lot of pre-defined varibles and we need to use them to supply userName and password it has to use to authenticate to the nodes.

### ansible_user : Pre-defined variable for userName 
### ansible_password : Predefined variable for password

.....
Variables should be passed to ansible by using the flag -e

        Eg : ansible -i INVENTORY all -e ansible_user=username -e ansible_password=password
            $ ansible -i inv all -e ansible_user=xyz -e ansible_password=xyz123 -m shell -a uptime/df -h

.....

Ansible is collection of modules / collections : whatever the task that you want to perform is already pre-defined, all you need is just to consume them.

There are 1000's of modules available : -m shell, -m yum, -m service    etc.,


### Ansible can be operated in 2 ways : 
.....
1) Manual Approach      : using ansible command  : With this you can execute one command at time.
2) Automated Approach   : using ansible playbook : With this we can mention all the set of tasks that needs to be executed, things will happen in the declared approach 
.....

## Automated Approach : This uses Playbook
.....

Playbooks are written using a language called YAML.

YAML is just  markup languaga ; Markup language is nothing a presentation language
.....

'YAML' is indendation specific

### Whai is playbook?
...
* Playbook : It is list of plays ( alwys starts with - )
* Play     : It is list of tasks
* Tasks    : An action that we wish to perform.
...

### How to run a playbook ?
...

ansible-playbook -i inventoryFileName -e ansible_user=userName -e ansible_password=password nameOfThePlaybook.yml
...

