# ivansible.dev_ansible

This role will install ansible in a virtual environment under user
home directory (as described in the
[installation guide](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#latest-releases-via-pip)),
put links to ansible binaries in the `~/bin` link directory
and add this directory on path in the user profile.


## Requirements

None


## Variables

Available variables are listed below, along with default values.

    dev_ansible_dir: ~/.ansible/venv

Directory with ansible virtual environment

    dev_ansible_link_dir: ~/bin

Directory to put links to ansible binaries

    dev_ansible_update_bashrc: true

Allows to add link directory on the local profile

    dev_ansible_python: python3

Python version to use for ansible: `python` or `python3`.


## Tags

- `dev_ansible_install` -- setup virtual environment and install ansible
- `dev_ansible_upgrade` -- upgrade old ansible 2.8 pre-installed on vagrant
- `dev_ansible_links` -- create links to ansible binaries
- `dev_ansible_bashrc` -- update path in the local profile
- `dev_ansible_all` -- all of above


## Dependencies

None


## Example Playbook

    - hosts: vag2
      roles:
        - role: ivansible.dev_ansible


## License

MIT


## Author Information

Created in 2018-2020 by [IvanSible](https://github.com/ivansible)
