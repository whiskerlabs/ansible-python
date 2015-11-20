# ansible-python

[![Ansible Galaxy](http://img.shields.io/badge/galaxy-whiskerlabs.python-660198.svg)](https://galaxy.ansible.com/list#/roles/4007)

An Ansible role for installing a sane Python execution environment.

This role installs (from source) target versions of the Python programming language,
Setuptools, and pip. Virtualenv is then installed with pip.

By default, the packaging tools (i.e. setuptools, pip, and virtualenv)
are upgraded to their latest versions. This functionality can be
disabled by setting the variable `python_upgrade_packaging_tools` to
`no`.

## Installation

`ansible-python` is tested with Ansible 1.9.x. It likely works on older
versions, but we haven't had occasion to check. README patches are
welcome if this requirement needs amending.

To install with Ansible Galaxy:

    $ ansible-galaxy install whiskerlabs.python

Or alternatively, add the path to a local copy of this repository to
`roles_path` within your project's `ansible.cfg` file:

    roles_path = /path/to/role_dir

where `/path/to/role_dir` is a parent directory of `ansible-python`.

Consult
[Ansible documentation](http://docs.ansible.com/intro_configuration.html)
for more info on how to configure `roles_path` in an Ansible
configuration file.

## Testing

A [Vagrantfile](http://docs.vagrantup.com/v2/vagrantfile/index.html)
is provided for testing the role within a VM during development. The
role is invoked by an
[Ansible provisioner](https://docs.vagrantup.com/v2/provisioning/ansible.html)
(via a test.yml example playbook) in a bare Ubuntu 14.04 virtual
machine.

Provided Vagrant and Virtualbox are installed, run `vagrant up` from
the root of this repository to launch and provision a VM. Run `vagrant
provision` to re-run the provisioner.

## Variables

A number of defaults and variables are provided to parameterize the
downloaded tarball paths, options passed to `configure` scripts, and
apt packages to install. See `defaults/main.yml` and `vars/main.yml`
for an exaustive list, but the following are the most likely knobs to
be turned:

    python_version (default: 2.7.10)
    python_setuptools_version (default: 18.5)
    python_pip_version (default: 7.1.2)
    python_virtualenv_version (default: 13.1.2)
    python_upgrade_packaging_tools: (default: yes)
    python_install_root (default: /usr/local)
    python_package_deps (default: [build-essential, libbz2-dev, libssl-dev, openssl, zlib1g-dev])

## Support

For questions or bug reports, please
[file an issue on Github](https://github.com/whiskerlabs/ansible-python/issues).

For any other inquiries, send mail to `software at whiskerlabs.com`.

## Credits

Installation procedure is, for the most part, cribbed from Brian
Wickman's
[bootstrap_python.sh script](https://github.com/wickman/python-bootstrap/).

## License

Copyright 2015 Whisker Labs

Licensed under the MIT License. See LICENSE for details.
