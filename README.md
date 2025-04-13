# Ansible Role: timesyncd

[![CI](https://github.com/AnyLinQ-B-V/ansible-role-timesyncd/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/AnyLinQ-B-V/ansible-role-timesyncd/actions/workflows/ci.yml)
[![MIT License](http://img.shields.io/badge/license-MIT-blue.svg?style=flat)](LICENSE)

Ansible role to install and configure systemd-timesyncd for time synchronization.

## Supported Platforms

  - Debian
    - Debian 12 (Bookworm)
    - Debian 13 (Trixie)
  - Ubuntu
    - Ubuntu 22.04 LTS (Jammy)
    - Ubuntu 24.04 LTS (Noble)

## Requirements

  - Ansible >= 2.10
  - systemd >= 216

## Role Variables

The default values for the variables are set in `defaults/main.yml`:
```yaml
timesyncd:
  servers:
    - 0.nl.pool.ntp.org
    - 1.nl.pool.ntp.org
    - 2.nl.pool.ntp.org
    - 3.nl.pool.ntp.org
```

## Dependencies

None.

## Example Playbook

```yaml
- name: Configure timesyncd
  hosts: all
  become: yes
  gather_facts: yes

  roles:
    - role: anylinq.timesyncd
      vars:
        timesyncd:
          servers:
            - 0.pool.ntp.org
            - 1.pool.ntp.org
```

## Testing

Tests are run using Molecule:

```bash
# Install dependencies
pip3 install -r requirements.txt

# Run tests
MOLECULE_DISTRO=debian12 molecule test
MOLECULE_DISTRO=ubuntu2404 molecule test
```

The CI pipeline automatically tests all supported distributions.

## License

MIT

## Changelog

See [CHANGELOG.md](https://github.com/AnyLinQ-B-V/ansible-role-timesyncd/blob/main/CHANGELOG.md) for a list of all notable changes to this project.

## Security

Please see our [Security Policy](https://github.com/AnyLinQ-B-V/ansible-role-timesyncd/blob/main/SECURITY.md) for reporting vulnerabilities.

## Contributing

Please read our [Contributing Guide](https://github.com/AnyLinQ-B-V/ansible-role-timesyncd/blob/main/CONTRIBUTING.md) and our [Code of Conduct](https://github.com/AnyLinQ-B-V/ansible-role-timesyncd/blob/main/CODE_OF_CONDUCT.md) before submitting a Pull Request.

---

<div align="center">
Created and maintained by <a href="https://www.anylinq.com">AnyLinQ B.V.</a><br/><br/>
<a href="https://www.anylinq.com"><img src="https://anylinq.com/hubfs/AnyLinQ%20transparant.png" width="120" alt="AnyLinQ Logo"/></a>
</div>

---

<sub>Author: Ronny Roethof (<a href="mailto:ronny@roethof.net">ronny@roethof.net</a>)</sub>
