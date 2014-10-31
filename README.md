# PostgreSQL Server (`postgresql-server`)

**Part of the BAS Ansible Role Collection (BARC)**

Installs PostgreSQL database server and optionally creates an 'app' db

## Overview

* Installs main and contrib PostgreSQL packages with python bindings required by ansible.
* Configures accounts for local users (controller and app) with superadmin and no permissions respectively.
* Optionally this role can create an 'app' database assigned to the app PostgreSQL user.

## Author

[British Antarctic Survey](http://www.antarctica.ac.uk) - Web & Applications Team

Contact: [basweb@bas.ac.uk](mailto:basweb@bas.ac.uk).

## Availability

This role is designed for internal use but if useful can be shared publicly.

## Branches

This project uses three permanent branches with the *Git Flow* branching model managing the interaction between branches.

* **Develop:** unstable, potentially non-working but most current version of roles. Bug fixes and features interact with this branch only.
* **Master:** stable, tested, working version of role with full documentation. Releases and hot fixes mainly interact with this branch. This branch should when consuming roles internally.
* **Public:** equivalent to the *master* branch, but available externally. Some configuration details may be altered or features removed to make available for public release.

## Testing

Manual testing is performed for all roles to ensure roles achieve their aims and this forms a prerequisite task for merging changes into the *master* and *public* branches.
Wherever possible testing is as complete as possible meaning tasks such as downloading dependencies are performed as part of each test.

## Issues

Please log issues to the [BAS Web and Applications Team](https://jira.ceh.ac.uk/browse/BASWEB) project in Jira, within the *Project - Ansible Roles* component.

If outside of NERC please get in touch to report any issues.

## Contributions

We have no formal contribution policy, if you spot any bugs or potential improvements please submit a pull request or get in touch.

These roles are used for internal projects which may dictate whether any contributions can be included.

## License

[Open Government Licence V2](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/2/)

## Requirements

### BAS Ansible Role Collection (BARC)

* `core`

## Variables

* `postgresql_server_controller_user_username`
    * The username of the controller OS user, used for system tasks, if enabled
    * This variable must be a valid OS user
    * Default: "controller"
* `postgresql_server_app_user_username`
    * The username of the app OS user, used for day to day tasks, if enabled
    * This variable must be a valid OS user
    * Default: "app"
* `postgresql_server_controller_postgresql_user_enabled`
    * If "true" a user for database server management tasks, termed a controller user, will be created with root privileges.
    * Default: true
* `postgresql_server_controller_mysql_user_username`
    * The username of the controller PostgreSQL user, used for managing the database server, if enabled
    * This variable must be a valid PostgreSQL user
    * Default: "controller"
* `postgresql_server_controller_postgresql_user_password`
    * Password for PostgreSQL controller user.
    * MUST NOT contain ":" or "\" characters to ensure compatibility with `.pgpass` files
    * Default: "stirring-up^the=flames$381194££iz€JQ4"
* `postgresql_server_app_postgresql_user_enabled`
    * If "true" a user for day to day database tasks, termed an app user, will be created with no initial privileges.
    * Default: true
* `postgresql_server_app_mysql_user_username`
    * The username of the app PostgreSQL user, used for day to day database tasks, if enable
    * This variable must be a valid PostgreSQL user
    * Default: "app"
* `postgresql_server_app_postgresql_user_password`
    * Password for PostgreSQL app user.
    * MUST NOT contain ":" or "\" characters to ensure compatibility with `.pgpass` files.
    * Default: "chase-PaX-87524"

* `postgresql_server_create_app_db`
    * If "true" a database named "app" will be created and assigned to the "app" postgres database user.
    * Default: "false"

## Changelog

### 0.1.9- October 2014

* Fixing incorrect variable value

### 0.1.8 - October 2014

* Updating dependencies
* App and controller users are now optional, enabled by default, their usernames are now set using variables
* Preparing for public release

### 0.1.7 - October 2014

* Adding missing state attribute for creating app database if desired

### 0.1.6 - October 2014

* Adding missing Ansible managed header to `pg_hba.conf` template
* Refactoring tasks

### 0.1.5 - October 2014

* Documentation update to fix outdated variable name references

### 0.1.4 - October 2014

* Updating default controller user password to be compatible with the .pgpass file format

### 0.1.3 - October 2014

* Role should not create an 'app' database by default, now corrected

### 0.1.2 - September 2014

* Correcting README

### 0.1.1 - September 2014

* Correcting name of task file

### 0.1.0 - September 2014

* Initial version
* Remote connections are not currently supported
