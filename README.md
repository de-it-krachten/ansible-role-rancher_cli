[![CI](https://github.com/de-it-krachten/ansible-role-rancher_cli/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-rancher_cli/actions?query=workflow%3ACI)


# ansible-role-rancher_cli

Installs Rancher CLI<br>
https://github.com/rancher/cli<br>



## Dependencies

#### Roles
None

#### Collections
None

## Platforms

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- CentOS 7
- RockyLinux 8
- RockyLinux 9
- OracleLinux 8
- OracleLinux 9
- AlmaLinux 8
- AlmaLinux 9
- SUSE Linux Enterprise 15<sup>1</sup>
- openSUSE Leap 15
- Debian 11 (Bullseye)
- Debian 12 (Bookworm)
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Ubuntu 24.04 LTS
- Fedora 39
- Fedora 40

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# Github CLI - API
rancher_cli_api: https://api.github.com/repos/rancher/cli

# Github CLI - repo
rancher_cli_repo: https://github.com/ranche/cli

# Lookup table for architecture
rancher_cli:
  architecture:
    x86_64: amd64
    i386: i386
    armv6l: arm
    armv7l: arm
    aarch64: arm64
  system:
    Linux: linux
    Darwin: darwin

# Construct filename based on the system & architecture
rancher_cli_file: "rancher-{{ rancher_cli_system }}-{{ rancher_cli_architecture }}-{{ rancher_cli_version }}.tar.gz"

# Version of the CLI to install
rancher_cli_version: latest

# Location/ownership/permissions of the binary
rancher_cli_path: /usr/local/bin/rancher
rancher_cli_owner: root
rancher_cli_group: root
rancher_cli_mode: '0755'
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'rancher_cli'
  hosts: all
  become: 'yes'
  tasks:
    - name: Include role 'rancher_cli'
      ansible.builtin.include_role:
        name: rancher_cli
</pre></code>
