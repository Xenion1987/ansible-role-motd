# Ansible role: motd

[![Ansible Galaxy downloads](https://img.shields.io/ansible/role/d/Xenion1987/motd?label=Galaxy%20downloads&logo=ansible&color=%23096598)](https://galaxy.ansible.com/ui/standalone/roles/Xenion1987/motd)
[![Ansible Galaxy](https://img.shields.io/badge/role-motd-000000.svg?logo=ansible)](https://galaxy.ansible.com/xenion1987/motd)
[![CI](https://github.com/xenion1987/ansible-role-motd/actions/workflows/ci.yml/badge.svg)](https://github.com/xenion1987/ansible-role-motd/actions/workflows/ci.yml)
[![License](https://img.shields.io/github/license/Xenion1987/ansible-role-motd)](https://github.com/Xenion1987/ansible-role-motd/blob/main/LICENSE)
[![Maintained](https://img.shields.io/badge/Maintained-yes-success.svg)](https://github.com/Xenion1987/ansible-role-motd)
[![Molecule](https://img.shields.io/badge/tested%20with-Molecule-blue.svg)](https://github.com/ansible-community/molecule)

This role creates a personalized message of the day.

## Table of contents

- [Requirements](#requirements)
- [Default Variables](#default-variables)
  - [motd_command](#motd_command)
  - [motd_file_dir](#motd_file_dir)
  - [motd_file_name](#motd_file_name)
  - [motd_file_path](#motd_file_path)
  - [motd_script_dir](#motd_script_dir)
  - [motd_script_name](#motd_script_name)
  - [motd_script_path](#motd_script_path)
  - [motd_service_description](#motd_service_description)
  - [motd_service_dir](#motd_service_dir)
  - [motd_service_name](#motd_service_name)
  - [motd_timer_delay_after_boot](#motd_timer_delay_after_boot)
  - [motd_timer_repeat_intervall](#motd_timer_repeat_intervall)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Requirements

- Minimum Ansible version: `2.12`

## Default Variables

### motd_command

Command's output will be forwarded into `motd_file_dir`.
May also be an absolute path to an executable script.

**_Type:_** string<br />

#### Default value

```YAML
motd_command: hostnamectl
```

#### Example usage

```YAML
- hostnamectl
- /path/to/custom/script
```

### motd_file_dir

Target dir to store the MOTD file

**_Type:_** string<br />

#### Default value

```YAML
motd_file_dir: /etc
```

#### Example usage

```YAML
- /usr/local/bin
- /home/user/.local/bin
```

### motd_file_name

Target MOTD file name

**_Type:_** string<br />

#### Default value

```YAML
motd_file_name: motd
```

### motd_file_path

MOTD target absolute path

**_Type:_** string<br />

#### Default value

```YAML
motd_file_path: '{{ motd_file_dir }}/{{ motd_file_name }}'
```

### motd_script_dir

Script's target absolute path

**_Type:_** string<br />

#### Default value

```YAML
motd_script_dir: /usr/local/bin
```

### motd_script_name

#### Default value

```YAML
motd_script_name: motd
```

### motd_script_path

#### Default value

```YAML
motd_script_path: '{{ motd_script_dir }}/{{ motd_script_name }}'
```

### motd_service_description

Unit file description

**_Type:_** string<br />

#### Default value

```YAML
motd_service_description: Generate message of the day
```

### motd_service_dir

Target dir to store the unit file

**_Type:_** string<br />

#### Default value

```YAML
motd_service_dir: /etc/systemd/system
```

#### Example usage

```YAML
- /etc/systemd/system
- /home/user/.config/systemd/user
```

### motd_service_name

Target unit file name

**_Type:_** string<br />

#### Default value

```YAML
motd_service_name: motd
```

### motd_timer_delay_after_boot

How long to delay service start after boot

**_Type:_** string<br />

#### Default value

```YAML
motd_timer_delay_after_boot: 2m
```

### motd_timer_repeat_intervall

Intervall to update the MOTD file

**_Type:_** string<br />

#### Default value

```YAML
motd_timer_repeat_intervall: 5m
```

## Dependencies

None.

## License

BSD, MIT

## Author

Xenion1987
