Ansible Role: raspbian common
=========

Common setup of Raspbian.
This role performs the followig tasks:

- Modify privilege of default user pi (tags: always)
- Change timezone (tags: timezone)
- Change hostname (tags: hostname)
- Install packages through apt-get (tags: apt)
- Install and configure florence (tags: florence, apt)

All the tasks need root privilege.

Requirements
------------

- Ansible (2.1.1)
- useradd
- userdel
- usermod


Role Variables
--------------

Available variables are listed below.

``` yaml
# hostname
raspbian_common_hostname: raspberrypi
# timezone
raspbian_common_timezone: 'Asia/Tokyo'
# Packages to be installed
raspbian_common_packages:
  - {name: florence}
  - {name: at-spi2-core}
  - {name: vim}
  - {name: git}
  - {name: fonts-takao}
  - {name: rsync}
```

Dependencies
------------

None

Example Playbook
----------------

``` yaml
- hosts: all
  vars_files:
      - vars/main.yml
  roles:
      - {role: raspbian_common, become: yes}
```


License
-------

MIT

