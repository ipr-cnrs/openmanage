## v1.X.Y

### Fix

* Use key_url instead of [deprecated SKS keyserver](https://sks-keyservers.net/).
* Truthy warnings with ansible-lint.

### Enhancements

* Repository version 10.1.0.0 for Debian Bullseye and Ubuntu Focal.

## v1.3.1

### Fix

* Add missing libncurses5 dependency.

## v1.3.0

### Enhancements

* Skip "Ensure to remove OpenManage related packages if requested" when it's not install (with package facts).
* Repositories for Debian Jessie and Ubuntu Trusty won't need modifications anymore with new OS release.
* Add support for Debian Buster and (not tested) Ubuntu Bionic (fix #1) with version 940.
* Manage SSL lib until Debian Stretch or Ubuntu Xenial (fix #2).
* Move packages related to 910 (Debian Stretch|Ubuntu Xenial) to a specific variable.

## v1.2.0

### Enhancements

* Install apt_key only if deploy_state = present.
* Remove all OpenManage related packages if deploy_state = absent.
* Packages installation don't need to restart service.

## v1.1.0

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
