# [Ansible role update](#ansible-role-update)

Install updates on your system.

|GitHub|GitLab|Downloads|Version|
|------|------|---------|-------|
|[![github](https://github.com/buluma/ansible-role-update/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-update/actions)|[![gitlab](https://gitlab.com/shadowwalker/ansible-role-update/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-update)|[![downloads](https://img.shields.io/ansible/role/d/buluma/update)](https://galaxy.ansible.com/buluma/update)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-update.svg)](https://github.com/buluma/ansible-role-update/releases/)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-update/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: true
  gather_facts: true

  roles:
    - role: buluma.update
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-update/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: Prepare
  hosts: all
  become: true
  gather_facts: false

  roles:
    - role: buluma.bootstrap
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-update/blob/master/defaults/main.yml):

```yaml
---
# defaults file for update

# For APT (Debian/Ubuntu) only: remove unused dependency packages for all module states except `build-dep'
update_autoremove: false

# For APT (Debian/Ubuntu) only: apt_upgrade type which can be: dist, full, true, or safe
update_upgrade_command: dist

# For APT (Debian/Ubuntu) only: update the apt cache if it's older than the cache_valid_time. Set in seconds.
update_cache_valid_time: 1

# When updating systems, a reboot may be required. Here you can select to:
# "true": Always reboot when packages have changed.
# "false": Never reboot when packages have changed.
update_reboot: true
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-update/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-bootstrap/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-bootstrap)|

## [Context](#context)

This role is part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-update/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[Alpine](https://hub.docker.com/r/buluma/alpine)|all|
|[Amazon](https://hub.docker.com/r/buluma/amazonlinux)|all|
|[EL](https://hub.docker.com/r/buluma/enterpriselinux)|all|
|[Debian](https://hub.docker.com/r/buluma/debian)|all|
|[Fedora](https://hub.docker.com/r/buluma/fedora)|all|
|[opensuse](https://hub.docker.com/r/buluma/opensuse)|all|
|[Ubuntu](https://hub.docker.com/r/buluma/ubuntu)|all|

The minimum version of Ansible required is 2.12, tests have been done on:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them on [GitHub](https://github.com/buluma/ansible-role-update/issues).

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-update/blob/master/LICENSE).

## [Author Information](#author-information)

[buluma](https://buluma.github.io/)

