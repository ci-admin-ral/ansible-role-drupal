# Ansible Role: Drupal

[![Build Status](https://img.shields.io/travis/thestarkenya/ansible-role-drupal.svg)](https://travis-ci.org/thestarkenya/ansible-role-drupal) [![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/thestarkenya/ansible-role-drupal/master/LICENSE)

Installs and configures Drupal on RHEL/CentOS ~~or Debian/Ubuntu~~.

## Requirements

None

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
drupal_core_dir: /var/www/html/drupal
drupal_core_owner: www-data
drupal_core_group: www-data

drupal_makefile_file: drupal.make.yml
drupal_makefile_force: false

drupal_profile_install: true
drupal_profile: minimal
drupal_profile_site_name: Drupal
drupal_profile_user: admin
drupal_profile_pass: hackme

drupal_settings_use_template: true
drupal_settings_hash_salt: 3bqNy7ia_UDClJ1hqSqu2iJfc5c8DF2uIpA-K1aAcTs
drupal_settings_database:
  host: localhost
  database: drupal
  username: root
  password: hackme
  driver: mysql
  prefix: ""
```

## Dependencies

- ansible-role-drush (https://github.com/thestarkenya/ansible-role-drush)

## Example Playbook

```yaml
- hosts: servers

  vars_files:
    - vars/main.yml

  roles:
    - role: ansible-role-drupal
```

Inside `vars/main.yml`:

```yaml
drupal_profile_site_name: Hello World

# ... etc ...
```

## License

MIT
