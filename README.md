# Ansible course

This repository contains excercises with Ansible.

<hr>

To change the default inventory to hosts-dev and not use -i option all time: create ansible.cfg

[More here](https://docs.ansible.com/ansible/latest/reference_appendices/config.html#ansible-configuration-settings)

<hr>

Checking the inventory configuration: `ansible --list-hosts`

NOTE: This also supports regular expressions and other types of calls, eg. `ansible --list-hosts app*`, `ansible --list-hosts webservers:loadbalancers`, `ansible --list-hosts \!control`, `ansible --list-hosts webservers[0]`

[More here](https://docs.ansible.com/ansible/latest/inventory_guide/intro_patterns.html)


