# PostgreSQL Server (`postgresql-server`)

**Part of the BAS Ansible Role Collection (BARC)**

Installs PostgreSQL database server and optionally creates an 'app' db

## Overview

* Installs *main* and *contrib* PostgreSQL packages with python bindings required by Ansible.
* Configures accounts for local users (controller and app) with super-admin and no permissions respectively.
* Optionally this role can create an 'app' database assigned to the app PostgreSQL user.

## Availability

This role is designed for internal use but if useful can be shared publicly.

## Usage

### Requirements

#### BAS Ansible Role Collection (BARC)

* `core`

### Variables

* `postgresql_server_controller_user_username`
    * The username of a controller user, used for system tasks, if enabled
    * This variable **MUST** be a valid UNIX username
    * Default: "controller"
* `postgresql_server_app_user_username`
    * The username of an app user, used for day to day tasks, if enabled
    * This variable **MUST** be a valid UNIX username
    * Default: "app"
* `postgresql_server_controller_postgresql_user_enabled`
    * If "true" a user for database server management tasks, termed a controller user, will be created with root privileges.
    * This is a binary variable and **MUST** be set to either "true" or "false" (without quotes).
    * Default: "true"
* `postgresql_server_controller_postgresql_user_username`
    * The username of the controller PostgreSQL user, used for managing the database server, if enabled
    * This variable **MUST** be a valid PostgreSQL username
    * Default: "controller"
* `postgresql_server_controller_postgresql_user_password`
    * Password for PostgreSQL controller user.
    * This **MUST NOT*** contain ":" or "\" characters to ensure compatibility with `.pgpass` files
    * Default: "password"
* `postgresql_server_app_postgresql_user_enabled`
    * If "true" a user for day to day database tasks, termed an app user, will be created with no initial privileges.
    * This is a binary variable and **MUST** be set to either "true" or "false" (without quotes).
    * Default: "true"
* `postgresql_server_app_postgresql_user_username`
    * The username of the app PostgreSQL user, used for day to day database tasks, if enable
    * This variable **MUST** be a valid PostgreSQL username
    * Default: "app"
* `postgresql_server_app_postgresql_user_password`
    * Password for PostgreSQL app user.
    * This **MUST NOT** contain ":" or "\" characters to ensure compatibility with `.pgpass` files
    * Default: "password"
* `postgresql_server_create_app_db`
    * If "true", an 'app' database will be created for your convenience
    * This is a binary variable and **MUST** be set to either "true" or "false" (without quotes).
    * Default: "false"
* `postgresql_server_app_db_name`
    * The name of the 'app' database
    * This variable **MUST** be a valid PostgreSQL database name.
    * Default: "app"
* `postgresql_server_app_db_owner`
    * The PostgreSQL user with ownership over the 'app' database, if enabled
    * This variable **MUST** be a valid PostgreSQL user
    * Default: "{{ postgresql_server_app_postgresql_user_username }}"

## Contributing

This project welcomes contributions, see `CONTRIBUTING` for our general policy.

## Developing

### Committing changes

The [Git flow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow/) workflow is used to manage development of this package.

Discrete changes should be made within *feature* branches, created from and merged back into *develop* (where small one-line changes may be made directly).

When ready to release a set of features/changes create a *release* branch from *develop*, update documentation as required and merge into *master* with a tagged, [semantic version](http://semver.org/) (e.g. `v1.2.3`).

After releases the *master* branch should be merged with *develop* to restart the process. High impact bugs can be addressed in *hotfix* branches, created from and merged into *master* directly (and then into *develop*).

### Issue tracking

Issues, bugs, improvements, questions, suggestions and other tasks related to this package are managed through the BAS Web & Applications Team Jira project ([BASWEB](https://jira.ceh.ac.uk/browse/BASWEB)).

## License

Copyright 2015 NERC BAS. Licensed under the MIT license, see `LICENSE` for details.