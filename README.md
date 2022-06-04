[![No Maintenance Intended](http://unmaintained.tech/badge.svg)](http://unmaintained.tech/)
# DEPRECATED/LOOKING FOR MAINTAINERS -> archived

[![Build Status - Master](https://travis-ci.org/juju4/ansible-caldera-agent.svg?branch=master)](https://travis-ci.org/juju4/ansible-caldera-agent)
[![Build Status - Devel](https://travis-ci.org/juju4/ansible-caldera-agent.svg?branch=devel)](https://travis-ci.org/juju4/ansible-caldera-agent/branches)(Syntax Only)

[![Appveyor - Master](https://ci.appveyor.com/api/projects/status/awmoxtb8nwg0ss8r?svg=true)](https://ci.appveyor.com/project/juju4/ansible-caldera-agent)
![Appveyor - Devel](https://ci.appveyor.com/api/projects/status/awmoxtb8nwg0ss8r/branch/devel?svg=true)
# Windows MITRE Caldera agent

Ansible role to setup MITRE Caldera agent on windows
https://github.com/mitre/caldera

## Requirements & Dependencies

### Ansible
It was tested on the following versions:
 * 2.4

### Operating systems

Only tested against Win10 and Ws2016 Evaluation.
Follow
http://kitchen.ci/blog/test-kitchen-windows-test-flight-with-vagrant/

## Example Playbook

Just include this role in your list.
For example

```
- host: all
  roles:
    - juju4.caldera-agent
```

Run
```
$ ansible -i inventory -m win_ping win --ask-pass
$ ansible-playbook -i inventory --limit win site.yml
```

## Continuous integration

This role has a travis basic test (for github, syntax check only) and a Vagrantfile (test/vagrant).

```
$ cd /path/to/roles/juju4.caldera-agent/test/vagrant
$ vagrant up
$ vagrant provision
$ vagrant destroy
$ ansible -i .vagrant/provisioners/ansible/inventory/vagrant_ansible_inventory -m win_ping -e ansible_winrm_server_cert_validation=ignore -e ansible_ssh_port=55986 all
```

## Troubleshooting & Known issues

* Ensure you follow ansible guide to be able to connect
http://docs.ansible.com/ansible/intro_windows.html

## FAQ

...

## License

BSD 2-clause
