Docker Installation Role
========================

An Ansible role to install Docker and Docker Compose on Linux systems.

Requirements
------------

- Ansible 2.1 or higher
- Target systems must be running a supported Linux distribution (Ubuntu, Debian, CentOS, RHEL, etc.)
- Internet access to download Docker packages

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
docker_users: []  # List of users to add to the docker group
docker_install_compose: true  # Whether to install Docker Compose
docker_compose_version: "v2.24.0"  # Version of Docker Compose to install
docker_edition: "ce"  # Docker edition (ce for Community Edition)
docker_package: "docker-{{ docker_edition }}"  # Package name to install
docker_service_name: "docker"  # Name of the Docker service
```

Dependencies
------------

None.

Example Playbook
----------------

Basic usage:

```yaml
- hosts: servers
  roles:
    - demo-role
```

With custom variables:

```yaml
- hosts: servers
  roles:
    - role: demo-role
      docker_users:
        - ubuntu
        - jenkins
      docker_install_compose: false
```

License
-------

GPL-2.0-or-later

Author Information
------------------

This role installs Docker using the official Docker repositories for maximum security and up-to-date packages.
