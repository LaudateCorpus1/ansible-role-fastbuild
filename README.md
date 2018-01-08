FASTBuild Role
==============

This role installs the [FASTBuild][fastbuild] build system software on the given
Ansible host.


Supported Host OS Types
-----------------------

Currently this role only supports Windows hosts, even though FASTBuild has alpha
support for Linux and Mac OS X.


Role Variables
--------------

This role defines the following variables which can be overridden:

- `fastbuild_arch`
- `fastbuild_version`
- `fastbuild_path_win`

See `defaults/main.yml` for further documentation of these variables.


[fastbuild]: http://fastbuild.org
