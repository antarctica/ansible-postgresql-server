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

## License

[Open Government Licence V2](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/2/)

## Requirements

### BAS Ansible Role Collection (BARC)

* `core`

## Variables

* `postgresql_server_controller_user_password`
    * Default password for controller user (i.e. root).
    * MUST NOT contain ":" or "\" characters to ensure compatibility with `.pgpass` files
    * Default: "stirring-up^the=flames$381194££iz€JQ4"

* `postgresql_server_app_user_password`
    * Default password for app user.
    * MUST NOT contain ":" or "\" characters to ensure compatibility with `.pgpass` files.
    * Default: "chase-PaX-87524"

* `postgresql_server_create_app_db`
    * If "true" a database named "app" will be created and assigned to the "app" postgres database user.
    * Default: "false"

## Changelog

### 0.1.8 - October 2014

* Updating dependencies

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
