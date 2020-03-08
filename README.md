# volume

[![Build Status](https://cloud.drone.io/api/badges/rolehippie/volume/status.svg)](https://cloud.drone.io/rolehippie/volume)

Ansible role to configure volume

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

None.

## License

Apache-2.0

## Author

Thomas Boerger
