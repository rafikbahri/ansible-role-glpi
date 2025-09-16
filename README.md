GLPI
====

A role to install and configure a GLPI server.

Requirements
------------

MySQL or MariaDB database.
Check Role Variables section to configure database connection.

Role Variables
--------------

Default variables are defined in `defaults/main.yml`.

Here are the relevant variables you might want to override:

```yaml
---
glpi_version: "10.0.19"
glpi_domain: glpi.example.com
glpi_db_host: localhost
glpi_db_name: glpi
glpi_db_user: glpi
glpi_db_port: 3306
glpi_db_password: glpi
glpi_timezone: Europe/Paris
glpi_volumes:
  - device: /dev/nvme1n1
    label: glpi-config
    mount_point: /mnt/glpi-config
    dir: /etc/glpi
  - device: /dev/nvme2n1
    label: glpi-data
    mount_point: /mnt/glpi-data
    dir: /var/lib/glpi
  - device: /dev/nvme3n1
    label: glpi-logs
    mount_point: /mnt/glpi-logs
    dir: /var/log/glpi
```

Dependencies
------------

None. This role installs all required packages, except the database server.
Database server installation might be a future improvement.

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
    - { role: rafikbahri.glpi }
```

License
-------

MIT

Author Information
------------------

- Name: Rafik Bahri
- Role: Senior DevOps Engineer
- Email: <rafikbahri.insat@gmail.com>
- Website: <https://rafikbahri.github.io>
- LinkedIn: <https://www.linkedin.com/rafik-bahri>
