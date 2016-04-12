Role Name
=========
[![license][2i]][2p]
[![twitter][3i]][3p]

A brief description of the role goes here.

Description
-----------

The role builds a nyc3-512MiB-centos7 droplet. However, it is very easy to make multiple copies with different id for each droplet. This allows to build say a docker swarm monstrosity or any other internetworked desire you may have. I chose centos, since it's my preferred provisioning client to use. You can change it to whatever you desire, though you could probably use better services that involve theother os client (aka the billions of deb based provisioners out there).

Role Variables
--------------

You don't change any variables in this role. However, you do include files that would have the variables. The reason is to allow for ease in reproduction.

``` yaml
# secret (where you keep your pubkey and your token for digitalocean)
secret:
  token: "token for digitalocean"
  key:
    id: "the key id of the pubkey from digitalocean"
    # required if you want to use 'ssh.yml' file
    pub: "{{ lookup('file', '~/.ssh/rsa.pub')}}"
    name: "name of the pubkey to be assigned with digitalocean"

# droplet information
vhost:
  name: "unique name of the droplet"
```

Requirements
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Usage
-----

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

``` yaml
- hosts: servers
    roles:
        - { role: username.rolename, x: 42 }
```

Author Information
------------------

[Alejandro Baez][1]

[1]: https://keybase.io/baez
[2i]: https://img.shields.io/badge/license-BSD_2-green.svg
[2p]: ./LICENSE
[3i]: https://img.shields.io/badge/twitter-a_baez-blue.svg
[3p]: https://twitter.com/a_baez
