---
layout: "panos"
page_title: "panos: panos_panorama_aggregate_interface"
description: |-
  Manages Panorama aggregate ethernet interfaces.
---

# panos_panorama_aggregate_interface

This resource allows you to add/update/delete Panorama aggregate ethernet interfaces.


## Import Name

```
<template>::<vsys>:<name>
```


## Example Usage

```hcl
resource "panos_panorama_aggregate_interface" "example" {
    template = "myTemplate"
    vsys = "vsys1"
    name = "ae5"
    mode = "layer3"
    static_ips = ["10.1.1.1/24"]
    comment = "Configured for internal traffic"
}
```

## Argument Reference

The following arguments are supported:

* `name` - (Required) The interface's name.
* `templaet` - (Required) The template where the interface should be.
* `vsys` - (Required) The vsys that will use this interface.  This should be
  something like `vsys1` or `vsys3`.
* `mode` - (Required) The interface mode.  Valid values are `layer3` (default),
  `layer2`, `virtual-wire`, `ha`, or `decrypt-mirror`.
* `netflow_profile` - (Optional) The netflow profile.
* `mtu` - (Optional) The MTU.
* `adjust_tcp_mss` - (Optional) Adjust TCP MSS (default: false).
* `ipv4_mss_adjust` - (Optional) The IPv4 MSS adjust value.
* `ipv6_mss_adjust` - (Optional) The IPv6 MSS adjust value.
* `enable_untagged_subinterface` - (Optional, bool) Set to `true` to enable
  untagged subinterfaces.
* `static_ips` - (Optional) List of static IPv4 addresses.
* `ipv6_enabled` - (Optional, bool) Set to `true` to enable IPv6.
* `ipv6_interface_id` - (Optional) The IPv6 interface ID.
* `management_profile` - (Optional) The management profile.
* `enable_dhcp` - (Optional, bool) Set to `true` to enable DHCP.
* `create_dhcp_default_route` - (Optional) Set to `true` to create a DHCP
  default route.
* `dhcp_default_route_metric` - (Optional) The metric for the DHCP default
  route.
* `comment` - (Optional) The interface comment.
* `decrypt_forward` - (Optional, bool, PAN-OS 8.1+) Set to `true` to enable decrypt forward.
* `dhcp_send_hostname_enable` - (Optional, PAN-OS 9.0+) For DHCP layer3 interfaces:
  enable sending the firewall or a custom hostname to DHCP server
* `dhcp_send_hostname_value` - (Optional, PAN-OS 9.0+) For DHCP layer3 interfaces:
  the interface hostname.  Leaving this unspecified with `dhcp_send_hostname_enable`
  set means to send the system hostname.
