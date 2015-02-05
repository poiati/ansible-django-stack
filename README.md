ansible-django-stack
====================

If you want a fast and easy way to deploy your Django application this role is for you. 

It will install and configure the following packages:

- nginx
- gunicorn
- supervisor

*Currently only supports python3.*

Role Variables
--------------

### server_name

*MANDATORY*

The public host of your website.

Example: www.example.com

### project_root_path

*MANDATORY*

The root of your Django project. In other words, where the `manage.py` is located.

Important: This path must be relative to your repository root path.

### repo

*MANDATORY*

The git repository to fetch the project from.

Example: git@github.com:poiati/example.git

### project_requirements_path

*OPTIONAL* | *DEFAULT 'requirements.txt'*

Your requirements file.

Important: This path must be relative to your repository root path.

Example Playbook
----------------

```yml
- hosts: webservers
  roles:
    - ansible-django-stack
  vars:
    server_name: gosuscores.com
    project_requirements_path: webapp/requirements.txt
    project_root_path: webapp/psngamesweb
    envs_path: /tmp/env
    static_path: /usr/local/share/public
    repo: git@github.com:poiati/psngames.git
    ssh_private_key_path: /Users/poiati/.ssh/id_rsa_deploy
```

License
-------

MIT

Author Information
------------------

Paulo Poiati

http://blog.paulopoiati.com
