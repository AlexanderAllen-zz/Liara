Liara
=============

Provides essential tools for LAMP stack development.

Requirements
------------

 - PHP
 - Ubuntu

Role Variables
--------------

In order to make LAMP configuration uniform across multiple playbooks, `AlexanderAllen.Liara` exposes
a variety of variables that tell other playbooks where things such as PHP configurations are located.

If you are using Vagrant, you can set these through your Vagrantfile, otherwise, you can set them in defaults/main.yml.

Variables are set in `defaults/main.yml` and `tasks/main.yml`.

Example Playbook
----------------

    - hosts: webservers
      roles:
         - { role: AlexanderAllen.Liara }

Usage with Vagrant
----------------

Example `Vagrantfile`:
    ...

      # Setup provisioning with an ansible playbook
      config.vm.provision "ansible" do |ansible|
        ansible.playbook = "liara.yml"
        ansible.groups = {
          "web" => "host1",
        }
        ansible.extra_vars = {
          "project_name" => project_name,
          "NEW_RELIC_LICENSE_KEY" => new_relic_license,
          "php_conf_dir" => php_conf_dir,
          "php_mod_dir" => php_mod_dir,
          "apc_stats_webdir" => apc_stats_webdir
        }
      end
    end

    ...

Example `liara.yml`:

    ---
    - hosts: host1
      roles:
        - { role: AlexanderAllen.Liara-Composer }
        - { role: AlexanderAllen.drupal-coding-standards }
        - { role: AlexanderAllen.Liara-Benchmarking }
        - { role: AlexanderAllen.Liara-ZendDebugger }
        - { role: AlexanderAllen.Liara-BDD }
        - { role: AlexanderAllen.Liara-Performance }

License
-------

GPLv2

Author Information
------------------

https://github.com/AlexanderAllen
