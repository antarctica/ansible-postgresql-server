# PostgreSQL Server (`postgresql-server`)

Installs PostgreSQL database server and optionally creates an 'app' db

## Overview

* Installs main and contrib PostgreSQL packages with python bindings required by ansible.
* Configures accounts for local users (controller and app) with superadmin and no permissions respectively.
* Optionally this role can create an 'app' database assigned to the app PostgreSQL user.

## Author

[British Antarctic Survey](http://www.antarctica.ac.uk) - Web & Applications Team

Contact: [basweb@bas.ac.uk](mailto:basweb@bas.ac.uk).

## Availability

Note: This role is for internal use only.

## License

[Open Government Licence V2](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/2/)

## Requirements

### BAS Ansible Role Collection (BARC)

* `core`

## Variables

* `postgres_controller_password`
    * Default password for controller user (i.e. root).
    * Default: "stirring-up^the*flames//381194//iz/JQ4"

* `postgres_app_password`
    * Default password for app user.
    * Default: "chase-PaX-87524"

* `postgres_create_app_db`
    * If "true" a database named "app" will be created and assigned to the "app" postgres database user. 
    * Default: "true"
 
## Changelog

### 0.1.0 - September 2014

* Initial version
* Remote connections are not currently supported

