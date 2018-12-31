# Ansible role `default-gate`

An Ansible role for configuring specific interface settings for linux systems. Specifically, the responsibilities of this role are to:

- Set interface protocol
- Set ip address
- Set netmask
- Set default gateway
- Define ipv6 settings
- etc.

## Requirements

Only works on RedHat like systems, no package or tools needed.

## Role Variables

This role is designed so it would be easy to debug any problems. Main purpose is to automatically set default gateway/router in an Ansible enviroment. This role has some global options that are mandatory for the role to apply the configured settings. For an example see the [example playbook](/example/example_playbook.yml). For more information about the possible options to use with the tags, visit the [RedHat](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/6/html/deployment_guide/s1-networkscripts-interfaces) customer portal.

| Variable   | Default | Comments (type)  |
| :---       | :---    | :---             |
| `config_network_interfaces` | false | Defines if the interface must be configured. |
| `enable_configured_interfaces_after_defining` | false | Defines if configs should be enabled. |
| `interfaces[]` | - | List with options for configuring interface. |

With this role you can precisely control wich options you want for what interface, completely automatically. For an example see the [example playbook](/example/example_playbook.yml). For more information about the possible options to use with the tags, visit the [RedHat](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/6/html/deployment_guide/s1-networkscripts-interfaces) customer portal.

| Variable   | Default | Comments (type)  |
| :---       | :---    | :---             |
| `name` | - | Name of the interface (eth1). |
| `configure` | - | Boolean that defines if the interface should be configured with these settings. |
| `enable` | - | Boolean that defines if the interface should be activated. |
| `method` | - | Defines option BOOTPROTO. |
| `defroute` | yes | Boolean that defines if this interface should have a default route. |
| `address` | - | IP-address for the interface. |
| `netmask` | - | Netmask fot the interface IP-address. |
| `gateway` | - | IP-address that should be set as default gateway. |
| `onboot` | yes | Defines if interface settings should be loaded when booted. |

## Dependencies

No dependencies.

## Example Playbook

See the test playbook in [example](/example/).

## Contributing

Issues, feature requests, ideas are appreciated and can be posted in the Issues section.

Pull requests are also very welcome. The best way to submit a PR is by first creating a fork of this Github project, then creating a topic branch for the suggested change and pushing that branch to your own fork. Github can then easily create a PR based on that branch. Don't forget to add your name to the contributor list below!

## License

2-clause BSD license, see [LICENSE.md](LICENSE.md)

## Contributors

- [Bert Van Vreckem](https://github.com/bertvv/) (maintainer skeleton)
- [Beachlessfawn2](https://github.com/Beachlessfawn2) (maintainer role)