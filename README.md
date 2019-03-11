enix.mongodb
=================

A role for deploying and configuring [mongodb](http://www.mongodb.com) and extensions on unix hosts using [Ansible](http://www.ansible.com/).


Requirements
------------

Supported targets:

- Ubuntu 16.04 "Xenial"
- Ubuntu 18.04 "Bionic"
- Debian 8 "Jessie"
- Debian 9 "Stretch"


Role Variables
--------------

This roles comes preloaded with almost every available default. You can override each one in your hosts/group vars, in your inventory, or in your play. See the annotated defaults in `defaults/main.yml` for help in configuration. All provided variables start with `mongodb__`.

- `mongodb__version` - MongoDB software version to install. This select the stable branch to select for installation. `defaults to 4.0`. currently available: 3.2, 3.4, 3.6, 4.0.
- `mongodb__packages` - MongoDB packages to install. `defaults to mongodb-org` which install everything. Can select the following: mongodb-org, mongodb-org-server, mongodb-org-mongos, mongodb-org-shell, mongodb-org-tools. see for details https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/.

Dependencies
------------

- None

Usage
-----

Use Ansible galaxy requirements.yml

    # mongodb from enix
    - src: enix.mongodb

And add it to your play's roles:

    - hosts: all
      roles:
        - role enix.mongodb:
            mongodb__version: 4.0

You can also use the role as a playbook. You will be asked which hosts to provision, and you can further configure the play by using `--extra-vars`.

    $ ansible-playbook -i inventory --extra-vars='{...}' main.yml

Still to do
-----------

- Write the role itself, for one


Changelog
---------

### 0.1

Initial version.

License
-------

GPLv2

Author Information
------------------

Laurent Corbes <laurent.corbes@enix.fr> - http://www.enix.io
