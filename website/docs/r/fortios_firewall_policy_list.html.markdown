---
layout: "fortios"
page_title: "FortiOS: fortios_firewall_policy_list"
sidebar_current: "docs-fortios-resource-firewall-policy-list"
subcategory: "FortiGate OldVersion"
description: |-
  Provides a resource to configure a list of firewall policies of FortiOS.
---

# fortios_firewall_policy_list
This resource supports Create/Read/Update/Delete of a list of firewall policies.  The attributes are all the same as `fortios_firewall_policy`.
The reason for creating this resource is so we dont have to have a different resource to move each policy as the list of policies will keep the order.
The major change with this resource is that policyid is a required field for each policy block


## Example Usage
```hcl
resource "fortios_firewall_policy_list" "main" {
  policy {
    policyid           = 1
    action             = "accept"
    logtraffic         = "utm"
    name               = "policys1"
    schedule           = "always"
    wanopt             = "disable"
    wanopt_detection   = "active"
    wanopt_passive_opt = "default"
    wccp               = "disable"
    webcache           = "disable"
    webcache_https     = "disable"
    wsso               = "enable"

    dstaddr {
      name = "all"
    }

    dstintf {
      name = "port4"
    }

    service {
      name = "HTTP"
    }

    srcaddr {
      name = "all"
    }

    srcintf {
      name = "port3"
    }
  }
}
```