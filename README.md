memoryleak.magento2
=========

A role to install Magento 2

Requirements
------------

None

Role Variables
--------------

```
---
# Whether to install Magento
magento2_execute_install: true
# Define the installation method: [git|composer]
magento2_installation_method: composer
# The URL to clone the git repository from:
magento2_installation_git_url: https://github.com/magento/magento2.git
# The version to checkout:
magento2_installation_git_version: 2.2
# The private key to use for git clone
magento2_installation_git_key: false
# Set which version should be installed: [community|enterprise]
magento2_installation_version: community
# Whether the file system ownership should be set: [true|false]
magento2_execute_filesystem_mode: false
# Whether to override the generated one:
magento2_override_env_file: false
# Whether to override the generated one:
magento2_override_config_file: false
# Path to media folder that is shared:
magento2_shared_media_folder: false
# Whether to install magento crons.
magento2_install_cron: true
# Whether to install magento crons for updating the system.
magento2_install_cron_update: true
# Whether to install magento crons for updating the web updater tasks.
magento2_install_cron_setup: true
# Path of Magento 2's installation parent folder:
magento2_installation_parent: /var/www
# Name of Magento 2's installation folder:
magento2_installation_name: magento2
# The file system user that should be used: [null]
# Requires:
# - magento2_execute_filesystem_mode: true
magento2_runtime_user: false
# The file system group that should be used: [null]
# Requires:
# - magento2_execute_filesystem_mode: true
magento2_runtime_group: false
# Whether to execute upgrade
magento2_execute_upgrade: true
# Whether to execute compilation
magento2_execute_compilation: true
# Whether to set the runmode
magento2_execute_runmode: true
# Set Magento runtime mode: [developer|production]
magento2_runtime_mode: production
# Whether to deploy content
magento2_execute_content_deploy: true
# Use the enforcement parameter for conent deployment [true|false]
magento2_execute_content_deploy_force: false
# Static content deploy strategy. Allowed values are: quick, standard, compact
magento2_static_deploy_strategy: quick
# Language to deploy content for
magento2_deploy_languages:
  - en_US
# Value to use for cli magento operations: memory limit
magento2_cli_memory_limit: 2048M
# Value to use for cli magento operations: timeout
magento2_cli_timeout: 3600
# Execute the initial magento setup:install: [true|No]
magento2_execute_setup: true
# Define the parameters and their values for the magento 2 setup:
magento2_setup_parameters:
  - name: base-url
    value: http://127.0.0.1/magento2/
  - name: db-host
    value: localhost
  - name: db-name
    value: magento
  - name: db-user
    value: magento
  - name: db-password
    value: magento
  - name: admin-firstname
    value: Magento
  - name: admin-lastname
    value: User
  - name: admin-email
    value: user@example.com
  - name: admin-user
    value: admin
  - name: admin-password
    value: admin123
  - name: language
    value: en_US
  - name: currency
    value: USD
  - name: timezone
    value: America/Chicago
  - name: use-rewrites
    value: "1"

magento2_magento_cli_commands:
  - setup:upgrade
  - setup:di:compile
  - setup:static-content:deploy -f en_US

```

Dependencies
------------

None

License
-------

BSD

Author Information
------------------

Haydar Ciftci <haydar.ciftci@gmail.com>
