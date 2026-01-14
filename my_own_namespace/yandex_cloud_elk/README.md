# Ansible Collection - my_own_namespace.yandex_cloud_elk

This collection contains a custom module and role for creating files with specified content.

## Modules

- `my_test` - Creates a file with specified content at the given path.

## Roles

- `my_module_role` - Role that uses the `my_test` module to create files.

## Installation

To install this collection, you can use the following command:

```bash
ansible-galaxy collection install my_own_namespace-yandex_cloud_elk-1.0.0.tar.gz
```

## Usage

### Using the module directly:

```yaml
- name: Create a file
  my_own_namespace.yandex_cloud_elk.my_test:
    path: "/tmp/testfile.txt"
    content: "This is test content.\n"
```

### Using the role:

```yaml
- name: Use my_module_role
  hosts: localhost
  gather_facts: false
  roles:
    - my_own_namespace.yandex_cloud_elk.my_module_role
```

Or with custom variables:

```yaml
- name: Use my_module_role with custom variables
  hosts: localhost
  gather_facts: false
  vars:
    file_path: "/tmp/custom_file.txt"
    file_content: "This is custom content.\n"
  roles:
    - my_own_namespace.yandex_cloud_elk.my_module_role
