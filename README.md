ansible-puppet
=========

An ansible role for managing the installation of `puppet-agent`.

More information on `puppet-agent` installation on various platforms can be found here:

  - [https://www.puppet.com/docs/puppet/8/install_agents#install_agents](https://www.puppet.com/docs/puppet/8/install_agents#install_agents)


Requirements
------------

This role requires `puppet-agent`  package to be supported on the target platform package to be avalible in package manager on the target systems othe than `Debian` and `Ubuntu`.

Example Playbook
----------------

### 1. All Options

This example shows all possible options and their default values on an `Ubuntu` system.

```yaml
---
- hosts: all
  roles:
    - role: rehanone.puppet
      vars:
        puppet:
          debug: true
          package:
            install_directory: "/opt/puppetlabs"
            name: puppet-agent
          service:
            enabled: false
            name: puppet
            state: stopped
          source:
            file: puppet8-release-jammy.deb
            package: puppet8-release
            url: https://apt.puppetlabs.com
          state: present
          system:
            binary_directory: "/usr/local/bin"

```

### 2. Minimum Required Options

This example shows minimum required options for using this role.

```yaml
---
- hosts: all
  roles:
    - role: rehanone.puppet
      vars:
        puppet:
```

License
-------

Apache-2.0
