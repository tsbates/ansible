# Ansible Role: IPsec VPN

This Ansible role configures an IPsec VPN on Cisco devices using Jinja2 templates. It automates the process of generating and applying the necessary configuration to establish a secure VPN connection.

## Requirements

- Ansible 2.9 or higher
- Cisco IOS device with appropriate permissions to apply configurations

## Role Variables

The role uses several variables that can be defined in `defaults/main.yml` or `vars/main.yml`. These variables include:

- `vpn_name`: The name of the VPN.
- `local_ip`: The local IP address of the device.
- `remote_ip`: The remote IP address of the VPN peer.
- `pre_shared_key`: The pre-shared key for authentication.

## Templates

The role includes a Jinja2 template located at `templates/ipsec_config.j2`, which defines the structure of the IPsec configuration. This template will be rendered using the variables defined in the role.

## Tasks

The main tasks of the role are defined in `tasks/main.yml`. The tasks include:

1. Rendering the IPsec configuration from the Jinja2 template.
2. Pushing the generated configuration to the Cisco device.

## Example Playbook

```yaml
- hosts: cisco_devices
  roles:
    - ipsec_vpn_role
```

## License

This role is licensed under the MIT License.

## Author Information

This role was created in 2023 by [Your Name].