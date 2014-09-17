Liara
=============

Provides essential tools for LAMP stack development.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

Required global variables:

 - liara_php_conf_dir: The dynamic *.ini include directory of your PHP install. For example: "/etc/php5/conf.d".
 - liara_php_mod_dir: The directory where your PHP *.so extension files are located. For example: "/usr/lib/php5/20090626".

Optional global variables:

 - liara_new_relic_license: The key for your New Relic account. If present New Relic will be enabled.
 - liara_apc_stats_webdir: If present, an HTML file for monitoring APC will be placed here.

If you are using Vagrant, you can set these through your Vagrantfile, otherwise, you can set them in defaults/main.yml.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: all
      roles:
         - { role: tooling, x: 42 }

License
-------

GPLv2

Author Information
------------------

https://github.com/AlexanderAllen
