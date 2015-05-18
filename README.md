sssd
====

Role which helps to install sssd - System Security Services Daemon.


Example
-------

```
---

# Default usage
- hosts: myhost1
  roles:
    - sssd

# Example of how to configure sssd
- hosts: myhost2
  vars:
    # Simply overwrite this variable with new configuration
    sssd_config:
        ...
        ...
  roles:
    - sssd
```


Role variables
--------------

List of variables used by the role:

```
# Package to be installed (you can force a specific version here)
sssd_pkg: sssd

# Default sssd config (you probably want to overwrite this)
sssd_config:
  sssd:
    domains: LOCAL
    services: nss
    config_file_version: 2
  nss:
    filter_groups: root
    filter_users: root
  'domain/LOCAL':
    id_provider: local
    auth_provider: local
    access_provider: permit
```


Dependencies
------------

* [Config Encoder Macros](https://github.com/picotrading/config-encoder-macros)


License
-------

MIT


Author
------

Jiri Tyr
