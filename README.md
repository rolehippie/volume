# volume

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/volume)
[![General Workflow](https://github.com/rolehippie/volume/actions/workflows/general.yml/badge.svg)](https://github.com/rolehippie/volume/actions/workflows/general.yml)
[![Readme Workflow](https://github.com/rolehippie/volume/actions/workflows/docs.yml/badge.svg)](https://github.com/rolehippie/volume/actions/workflows/docs.yml)
[![Galaxy Workflow](https://github.com/rolehippie/volume/actions/workflows/galaxy.yml/badge.svg)](https://github.com/rolehippie/volume/actions/workflows/galaxy.yml)
[![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/volume)](https://github.com/rolehippie/volume/blob/master/LICENSE)
[![Ansible Role](https://img.shields.io/badge/role-rolehippie.volume-blue)](https://galaxy.ansible.com/rolehippie/volume)

Ansible role to format and mount disks/volumes.

## Sponsor

Building and improving this Ansible role have been sponsored by my current and previous employers like **[Cloudpunks GmbH](https://cloudpunks.de)** and **[Proact Deutschland GmbH](https://www.proact.eu)**.

## Table of content

- [Requirements](#requirements)
- [Default Variables](#default-variables)
  - [volume_partitions](#volume_partitions)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Requirements

- Minimum Ansible version: `2.10`

## Default Variables

### volume_partitions

List of volume partitions

#### Default value

```YAML
volume_partitions: []
```

#### Example usage

```YAML
volume_partitions:
  - name: mysql
    number: 1
    path: /var/lib/mysql
    label: msdos
    filesystem: ext4
    device: /dev/sdb
    options:
      - discard
      - nofail
      - defaults
  - name: foobar
    number: 1
    path: /var/lib/foobar
    label: gpt
    filesystem: ext4
    device: /dev/sdc
    state: present
    part_start: 0%
    part_end: 100%
    part_type: primary
    unit: %
    flags: []
    options:
      - discard
      - nofail
      - defaults
```

## Discovered Tags

**_volume_**

## Dependencies

- [ansible.posix](https://github.com/ansible-collections/ansible.posix)
- [community.general](https://github.com/ansible-collections/community.general)

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
