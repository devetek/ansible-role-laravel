Ansible role: Laravel
=========

This role installs Laravel using the official Composer installer (composer create-project laravel/laravel) and places it in the desired directory.

Requirements
------------

This role depends on the following Ansible roles to be applied beforehand:

- A PHP role (e.g., [geerlingguy.php]) – to install and configure PHP
- A web server role (e.g., `nginx`, `apache`) – to serve the Laravel application
- A Composer role (e.g., [geerlingguy.composer]) – to install PHP dependencies

Role Variables
--------------

List of variables in ansible-role-laravel:

```sh
---
laravel_source: cli # cli or source (URL)
laravel_version: "12.0.8"
laravel_install_path: /var/www/laravel
laravel_owner: www-data
laravel_group: www-data

laravel_php_executable: /usr/bin/php8.4
laravel_composer_executable: /usr/local/bin/composer

```

Dependencies
------------

This role depends on the following Ansible roles:

- `php_installer`: Installs and configures PHP
- `composer_installer`: Installs Composer

> ⚠️ **Make sure both `php_installer` and `composer_installer` roles are available and properly configured before using this role.**

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
    - geerlingguy.php
    - geerlingguy.composer
    - devetek.laravel
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

[Nedya Prakasa]. Role created for [dPanel].

[dPanel]: https://cloud.terpusat.com/
[Nedya Prakasa]: https://github.com/prakasa1904
[devetek]: https://github.com/devetek
[geerlingguy.php]: https://galaxy.ansible.com/ui/standalone/roles/geerlingguy/php/
[geerlingguy.composer]: https://galaxy.ansible.com/ui/standalone/roles/geerlingguy/composer/