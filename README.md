# Ansible course

This repository contains excercises with Ansible - Configuration Automation Tool.

<hr>

To change the default inventory to hosts-dev and not use -i option all time: create ansible.cfg

[More here](https://docs.ansible.com/ansible/latest/reference_appendices/config.html#ansible-configuration-settings)

<hr>

Checking the inventory configuration: `ansible --list-hosts`

NOTE: This also supports regular expressions and other types of calls, eg. `ansible --list-hosts app*`, `ansible --list-hosts webservers:loadbalancers`, `ansible --list-hosts \!control`, `ansible --list-hosts webservers[0]`

[More here](https://docs.ansible.com/ansible/latest/inventory_guide/intro_patterns.html)

<hr>

## Ansible tasks

* Basic building blocks of ansible execution.
* Oneliers for checking host status.
* They retrive return status of executed commands
* Tasks can be defined in playbooks

eg. `ansible -m ping all`

^ use module ping for inventory

<hr>

## Playbooks

Recepie for certain host groups, ordered from first to last.

They are composed from plays (map of host-tasks). In plays modules are used (eg. copy, service, etc.)

eg. `ansible-playbook playbooks/ping.yml`

<hr>

## Serice handlers

Listeners for service config change. If change is made - service action is performed. Othervise service action is skipped

<hr>

## Compose multiple playbooks

Compose playbooks for one system in single playboook file. This happens via importing subsequent playbooks

<hr>

## Variables

Ansible provides ANSIBLE_FACTS variable with all metadata about host.  

Status module provides view into gathered information, eg. `ansible -m setup app1`  

Jinja2 templating is used to evaluate variables.

Local variables are created with `vars:`as key-value pairs. 

Variables can be registered from tasks by `register: *name_of_variable*`. They will contain outputs from it's task

Debug module displays variables contents and playbook information.  

* [Using Variables](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_variables.html)
* [Register Variables](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_variables.html#registering-variables)
* [Debug mode](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/debug_module.html)

<hr>

## Roles

Used to group tasks together. Clean directory structure. Break configuration into files. Reuse code in similar configurations. Easy to modify and reduce syntax errors.

Initalize directory structure `ansible-galaxy role init roles/webservers`

It's a great way to write configuration in modular way.
