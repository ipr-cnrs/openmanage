# Openmanage

1. [Overview](#overview)
2. [Role Variables](#role-variables)
3. [Example Playbook](#example-playbook)
4. [Configuration](#configuration)
5. [Development](#development)
6. [License](#license)
7. [Author Information](#author-information)

## Overview

A role to manage OpenManage (via omreport, omconfig,…), it's web interface OMSA (OpenManage Server Administrator) and iDrac (with racadm)

## Role Variables

* **openmanage__repositories** : List of APT repositories that can provide OpenManage. Each entry is a dict [default : `See default/main.yml`].
* **openmanage__deploy_state** : The desired state this role should achieve [default for Dell hardware : `present`].
* **openmanage__install_recommends** : If recommended packages should be install [default : `False`].
* **openmanage__dep_packages** : List of dependencies packages to be able to run racadm [default : `See default/main.yml`].
* **openmanage__base_packages** : List of base packages for all racadm base usage [default : `See default/main.yml`].
* **openmanage__ssl_packages** : List of SSL related packages to fix some dependencies on old versions [default : `See default/main.yml`].
* **openmanage__webgui_state** : The desired state for web interface of OMSA [default  : `absent`].
* **openmanage__webgui_packages** : List of packages to provide web interface to OMSA [default : `See default/main.yml`].
* **openmanage__webgui_service_name** : Name of the systemd unit to manage web interface [default : `dsm_om_connsvc`].

## Example Playbook

* Use defaults vars :

``` yaml
- hosts: mynode.DOMAIN
  roles:
    - role: ipr-cnrs.openmanage
      tags: ['role::openmanage', 'ipr', 'idrac']
```

* Enable web interface for OMSA (on https://<ip_address>:1311/) :

``` yaml
- hosts: mynode.DOMAIN
  roles:
    - role: ipr-cnrs.openmanage
      openmanage__webgui_state: "present"
      tags: ['role::openmanage', 'ipr', 'idrac']
```

## Configuration

This role will :
* Add an APT repository in order to provide OpenManage.
* Install dependencies packages.
* Install basic packages for all racadm usage.
* Start dataeng service to be able to use OpenManage applications (omreport, omconfig,…).
* Install and enable web interface on https://<ip_address>:1311 if requested.
* Fix idrac7's executable permissions.
* Fix libssl error RAC1170 (until Debian Stretch or Ubuntu Xenial).
* Set up symlinks to be able to run apps from $PATH.

## Development

This source code comes from our [Gogs instance][openmanage source] and the [Github repo][openmanage github] exist just to be able to send the role to Ansible Galaxy…

But feel free to send issue/PR here :)

Thanks to this [hook][gogs to github hook], Github automatically got updates from our [Gogs instance][openmanage source] :)

Thanks to @roumano

## License

[WTFPL][wtfpl website]

## Author Information

Jérémy Gardais
* Source : [on IPR's Gogs][openmanage source]
* [IPR][ipr website] (Institut de Physique de Rennes)

[gogs to github hook]: https://stackoverflow.com/a/21998477
[openmanage source]: https://git.ipr.univ-rennes1.fr/cellinfo/ansible.openmanage
[openmanage github]: https://github.com/ipr-cnrs/openmanage
[wtfpl website]: http://www.wtfpl.net/about/
[ipr website]: https://ipr.univ-rennes1.fr/
