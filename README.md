cdriehuys.ufw
=========

Install and configure UFW.

Requirements
------------

None.

Role Variables
--------------

The following are the variables used by the role and their defaults.

```YAML
apt_cache_time: 3600
ssh_port: 22
```

Common variables used across roles.

```YAML
ufw_rules: []
ufw_default_rules:
  - direction: incoming
    policy: deny
  - port: "{{ ssh_port }}"
    rule: limit
```

Typical customization of the rules should be done by modifying the `ufw_rules` variable. Each entry accepts the arguments: `direction`, `policy`, `port`, `proto`, and `rule`.

Dependencies
------------

None.

Example Playbook
----------------

To run the role, include it as follows.

    - hosts: all
      roles:
         - cdriehuys.ufw

License
-------

MIT

Author Information
------------------

Chathan Driehuys (cdriehuys@gmail.com)
