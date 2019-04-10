## v1.X.Y

### Enhancements
* Allow to install web interface for OMSA.
* Install idrac8 (and above) package by default.
* Install libssl.1.0.0 from Dell repo as base package.
* Install libxslt1.1 as dependency for om.* apps.
* Manage systemd service that provide the web interface.
* Manage dataeng service to be able to use OpenManage apps.
* Manage apps's symlinks to be able to run from $PATH.

## v1.0.2

### Fix

* Set the correct issue url.

## v1.0.1

### Fix
* Fix E405 Remote package tasks should have a retry.

## v1.0.0

### Features
* Add linux.dell.com repo
* Set "present" state for Dell hardware (exclude virtual host)
* Install dependencies packages
* Install base packages for all racadm usage
* Fix libssl error RAC1170
