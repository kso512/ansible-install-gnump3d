[![Build Status](https://travis-ci.org/kso512/ansible-install-gnump3d.svg?branch=master)](https://travis-ci.org/kso512/ansible-install-gnump3d)

# [ansible-install-gnump3d](https://galaxy.ansible.com/kso512/ansible-install-gnump3d/)

An [Ansible](https://www.ansible.com/) [Role](http://docs.ansible.com/ansible/playbooks_roles.html#roles) to install the [GNUMP3d](http://https://www.gnu.org/software/gnump3d/) application from source.

I do **NOT** recommend the default configuration for unprotected connection directly to the Internet, as the server configuration includes access without encryption.

## Requirements

If the server has a firewall enabled, it may need to be altered to allow incoming packets on TCP ports 8888.  No music or play lists are included, so you'll need to supply those.  See the *Role Variables* section below for those locations.

## Role Variables

The defaults shown below work "out-of-the-box" and only need customization if they don't meet your needs.

| Name | Description | Default Value |
| ---- | ----------- | ------------- |
| ansible_install_gnump3d_apt_prereqs | List of APT packages to install | (See **NOTE A** below) |
| ansible_install_gnump3d_conf | Fully-qualified file name of the GNUMP3d configuration file | /etc/gnump3d/gnump3d.conf |
| ansible_install_gnump3d_conf_src | Relative or fully-qualified file name of the GNUMP3d configuration file source | gnump3d.conf.j2 |
| ansible_install_gnump3d_executable | Fully-qualified file name of the GNUMP3d executable | /usr/bin/gnump3d |
| ansible_install_gnump3d_systemd_service_dest | Fully-qualified file name of the GNUMP3d systemd service unit file | /lib/systemd/system/gnump3d.service |
| ansible_install_gnump3d_systemd_service_src | Relative or fully-qualified file name of the GNUMP3d systemd service unit file source | systemd.gnump3d.service.j2 |

**NOTE A**

List of APT packages installed as pre-requisites:

- cmake
- perl-modules

## Dependencies

This role depends on no other roles.

## Example Playbook

Configure a GNUMP3d server:

    - hosts: music-server
      roles:
        - { role: kso512.ansible-install-gnump3d }

## License

BSD

## Author Information

> Chris Lindbergh @kso512

