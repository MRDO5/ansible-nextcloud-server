# ansible-nextcloud-server

ansible-nextcloud-server-role


This role help you install nextcloud with nginx and all other needed packages with configuration.

In defaults/main.yml you can change variable nextcloud_version:  for install other versions you want.

This role configure php and php-fpm for nextcloud. If you want make changes in php or php-fpm you can add that in yaml in directory tasks 

Before installation or run this role you need install and configure your DB(database) for enterprise. I have using in my server mysql how recommended in documentation.


After install DB you need create for role install file like this:

example: install-nextcloud.yml


```
---
  - hosts: centos
    gather_facts: yes
		become: yes

    roles:
      - nextcloud
...
```

and have inventory file where you write information about your host or server where you want make install:

example:  inventory.yml
```
[localserver]
localhost

[centos]
nextcloud  ansible_host=192.168.88.235 ansible_port=22 ansible_user=deploy
```

