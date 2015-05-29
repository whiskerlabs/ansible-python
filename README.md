# ansible-python

An Ansible role for installing a sane Python execution environment.

This role installs target versions of the Python programming language,
Setuptools, and pip, all from source. Virtualenv is then installed
with pip. Its tasks largely comprise the installation process set
forth by
[Brian Wickman's bootstrap_python.sh script](https://github.com/wickman/python-bootstrap/).

## Requirements

Tested on Ansible 1.9.x.

## Installation

With Ansible Galaxy:

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

A Vagrantfile is provided for use in testing the role during
development. With it, this role's tasks are run (via a test.yml
example playbook)in a bare Ubuntu 14.04 virtual machine.

Simply run `vagrant up` from the root of this repository to launch and
provision a VM.

## Variables

A number of defaults and variables are provided to parameterize the
downloaded tarball paths, options passed to `configure` scripts, and
apt packages to install. See `defaults/main.yml` and `vars/main.yml`
for an exaustive list, but the following are the most likely knobs to
be turned:

    python_version (default: 2.7.9)
    python_setuptools_version (default: 12.0.5)
    python_pip_version (default: 6.0.8)
    python_install_root (default: /usr/local)
    python_package_deps (default: [build-essential, libbz2-dev, libssl-dev, openssl, zlib1g-dev])
