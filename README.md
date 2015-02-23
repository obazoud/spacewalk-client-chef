spacewalk-client Cookbook
=========================
This cookbook installs and registers a node as a Spacewalk client.

Requirements
------------
- Ubuntu 12.04, 14.04
- CentOS/RHEL 5,6,7

Attributes
----------
```
default['spacewalk']['pkg_source_path'] = Chef::Config[:file_cache_path]
default['spacewalk']['reg']['key'] = "my_activation_key"
default['spacewalk']['reg']['server'] = "my_spacewalk_server"
```

Usage
-----
#### spacewalk-client::rhel
Include `spacewalk-client::rhel` in your node's `run_list` and set the default['spacewalk']['reg'] attributes.

#### spacewalk-client::ubuntu

Include `spacewalk-client::ubuntu` in your node's `run_list` and set the default['spacewalk']['reg'] attributes.

For 12.04 only, make sure you somehow (cookbook\_file, remote\_file..) put the following files in default['spacewalk']['pkg\_source\_path']
- apt-transport-spacewalk-1.0.6-2.all-deb.deb
- python-ethtool-0.11-2.amd64-deb.deb
- python-rhn-2.5.55-2.all-deb.deb
- rhn-client-tools-1.8.26-4.amd64-deb.deb
- rhnsd-5.0.4-3.amd64-deb.deb

You can build them yourself like described here
http://www.devops-blog.net/spacewalk/registering-ubuntu-and-debian-servers-with-spacewalk

License and Authors
-------------------
Authors: Phil Schuler http://devops-blog.net
