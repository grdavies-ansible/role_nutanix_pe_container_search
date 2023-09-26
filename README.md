# Nutanix Role to search for a container UUID from a name

This Ansible role will search for a container UUID based on the supplied container name.

## Input Variables

| Variable                                           | Required | Default | Choices                   | Comments                                                                             |
|----------------------------------------------------|----------|---------|---------------------------|--------------------------------------------------------------------------------------|
| nutanix_role_prism_container_search_host           | yes      |         |                           | The IP address or FQDN for the Prism (Element only) which you want to connect.       |
| nutanix_role_prism_container_search_username       | yes      |         |                           | A valid username with appropriate rights to access the Nutanix API.                  |
| nutanix_role_prism_container_search_password       | yes      |         |                           | A valid password for the supplied username.                                          |
| nutanix_role_prism_container_search_port           | no       | 9440    |                           | The Prism TCP port.                                                                  |
| nutanix_role_prism_container_search_validate_certs | no       | no      | true / false              | Whether to check if Prism UI certificates are valid.                                 |
| nutanix_role_prism_container_search_name           | yes      |         |                           | Name of container to search for.                                                     |

## Output Variables

| Variable                                       | Required | Default | Choices                   | Comments                                                                            |
|------------------------------------------------|----------|---------|---------------------------|-------------------------------------------------------------------------------------|
| nutanix_role_prism_container_search_found_uuid |          |         |                           | If a container is found its UUID will be returned in this variable                  |

## Dependencies

- grdavies.role_nutanix_prism_api

## Example Playbook

```
- hosts: localhost
  gather_facts: false
  roles:
    - grdavies.role_nutanix_pe_container_search
  vars:
    nutanix_role_prism_container_search_host: 10.38.185.37
    nutanix_role_prism_container_search_username: admin
    nutanix_role_prism_container_search_password: nx2Tech165!
    nutanix_role_prism_container_search_name: Default
```

## License

See LICENSE.md

## Author Information

Ross Davies
