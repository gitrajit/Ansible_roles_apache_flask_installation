# Ansible_roles_apache_flask_installation
Ansible roles to install apache and deploy flask code


##Steps:
* Install Apache , libapache2-mod-wsgi to enable mod_wsgi for flask and python-pip for installing python packages

```
name: install packages
  package: name={{ item  }} state=present update_cache=no
  with_items:
    - apache2
    - libapache2-mod-wsgi
    - python-pip

```

* Install flask using pip module

```
- pip: name={{ item }}
  with_items:
      - flask
```

* Deploy the falsk code and start the apache

