# volume

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/volume) [![Build Status](https://img.shields.io/drone/build/rolehippie/volume/master?logo=drone)](https://cloud.drone.io/rolehippie/volume) [![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/volume)](https://github.com/rolehippie/volume/blob/master/LICENSE) 

Ansible role to format and mount disks/volumes. 

## Sponsor 

[![Proact Deutschland GmbH](https://proact.eu/wp-content/uploads/2020/03/proact-logo.png)](https://proact.eu) 

Building and improving this Ansible role have been sponsored by my employer **Proact Deutschland GmbH**.

## Table of content

* [Default Variables](#default-variables)
  * [volume_partitions](#volume_partitions)
* [Dependencies](#dependencies)
* [License](#license)
* [Author](#author)

---

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
    filesystem: ext4
    device: /dev/sdb
    options:
      - discard
      - nofail
      - defaults
  - name: foobar
    number: 1
    path: /var/lib/foobar
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

## Dependencies

* None

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
