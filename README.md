# Openmanage

1. [Overview](#overview)
2. [Role Variables](#role-variables)
3. [Example Playbook](#example-playbook)
4. [Configuration](#configuration)
5. [Development](#development)
6. [License](#license)
7. [Author Information](#author-information)

## Overview

A role to manage Openmanage installation and configuration.

## Role Variables

* **
openmanage__repositories** : List of APT repositories that can provide OpenManage. Each entry is a dict [default : `See default/main.yml`].
* **openmanage__base_packages** : List of base packages in order to provide Openmanage [default : `openmanage`].
* **openmanage__deploy_state** : The desired state this role should achieve. [default for Dell hardware : `present`].

## Example Playbook

* Use defaults vars :

``` yaml
- hosts: mynode.DOMAIN
  roles:
    - role: ipr-cnrs.openmanage
      tags: ['role::openmanage', 'ipr', 'idrac']
```

## Configuration

This role will :
* Add an APT repository in order to provide OpenManage.

## Development

This source code comes from our [Gogs instance][openmanage source] and the [Github repo][openmanage github] exist just to be able to send the role to Ansible Galaxy…

But feel free to send issue/PR here :)

Thanks to this [hook][gogs to github hook], Github automatically got updates from our [Gogs instance][openmanage source] :)

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
