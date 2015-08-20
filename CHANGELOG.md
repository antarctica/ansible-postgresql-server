# PostgreSQL Server (`postgresql-server`) - Changelog

## 0.2.0 - August 2015

* Updating default password variables for consistency to highlight they should be changed
* Tidying up README

## 0.1.13 - March 2015

* Fixing tasks to prevent unnecessary change reporting

## 0.1.12 - December 2014

* Allowing owner and name of app db to be configurable
* Added missing OS package requirement

## 0.1.11 - December 2014

* Preparing role for public release

## 0.1.10- November 2014

* Fixing incorrect variable value

## 0.1.9- October 2014

* Fixing incorrect variable value

## 0.1.8 - October 2014

* Updating dependencies
* App and controller users are now optional, enabled by default, their usernames are now set using variables
* Preparing for public release

## 0.1.7 - October 2014

* Adding missing state attribute for creating app database if desired

## 0.1.6 - October 2014

* Adding missing Ansible managed header to `pg_hba.conf` template
* Refactoring tasks

## 0.1.5 - October 2014

* Documentation update to fix outdated variable name references

## 0.1.4 - October 2014

* Updating default controller user password to be compatible with the .pgpass file format

## 0.1.3 - October 2014

* Role should not create an 'app' database by default, now corrected

## 0.1.2 - September 2014

* Correcting README

## 0.1.1 - September 2014

* Correcting name of task file

## 0.1.0 - September 2014

* Initial version
* Remote connections are not currently supported
