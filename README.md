Ansible role ableton.fastbuild
==============================

This role installs [FASTBuild][fastbuild] on a Windows-based host.

Requirements
------------

Ansible >= 2.10, and a [Windows-based host][ansible-win].

Although FASTBuild has support for Linux and macOS hosts, this role doesn't support those
platforms yet.

Role Variables
--------------

The following variables influence how FASTBuild is installed on the host:

- `fastbuild_arch`: Architecture to download, must be either `x64` or `x86`.
- `fastbuild_cache_dir`: Where FASTBuild should store its cache.
- `fastbuild_cache_owner`: User who will own the FASTBuild configuration directory.
- `fastbuild_cache_schedule_trim`: If `true`, then add a scheduled task to regularly trim
  the cache.
- `fastbuild_cache_trim_size_mb`: How large the FASTBuild cache should be trimmed to
  (requires `fastbuild_cache_schedule_trim` to be `true`).
- `fastbuild_path_win`: Where the FASTBuild executables will be extracted to.
- `fastbuild_version`: Version of FASTBuild to install.

See the [`defaults/main.yml`](defaults/main.yml) file for full documentation on required
and optional role variables.

Example Playbook
----------------

```yaml
---
- name: Install FASTBuild on hosts
  hosts: "all"
  vars:
    fastbuild_cache_schedule_trim: true
    fastbuild_cache_trim_size_mb: 4096
    fastbuild_path_win: C:\FASTBuild
    fastbuild_version: "1.05"

  roles:
    - ableton.fastbuild
```

License
-------

MIT

Maintainers
-----------

This project is maintained by the following GitHub users:

- [@ala-ableton](https://github.com/ala-ableton)
- [@nre-ableton](https://github.com/nre-ableton)


[ansible-win]: https://docs.ansible.com/ansible/latest/user_guide/windows_setup.html
[fastbuild]: https://fastbuild.org/
