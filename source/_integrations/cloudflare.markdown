---
title: Cloudflare
description: Automatically update your Cloudflare DNS records.
ha_category:
  - Network
ha_release: 0.74
ha_iot_class: Cloud Push
ha_codeowners:
  - '@ludeeus'
  - '@ctalkington'
ha_domain: cloudflare
ha_config_flow: true
ha_integration_type: integration
---

With the Cloudflare integration, you can keep your Cloudflare DNS records up to date.

The integration runs every hour, but can also be triggered by running the {% my developer_services title="`cloudflare.update_records` service" service="cloudflare.update_records" %}.

## Requirements

The setup requires an API Token created with `Zone:Zone:Read` and `Zone:DNS:Edit` permissions for all zones in your account.

An easy way to create this is to start with the "Edit zone DNS" template then add `Zone:Zone:Read` to the permissions.

[Cloudflare API Tokens Guide](https://developers.cloudflare.com/api/tokens/create)

{% include integrations/config_flow.md %}

## Additional information

### Usage of external service

This platform uses the API from [ipify.org](https://www.ipify.org/) to set the public IP address.

### Limitations

#### Unusable TLDs

Due to a limitation in the Cloudflare API, you can not use this integration with any of the following TLD's:

- `.cf`
- `.ga`
- `.gq`
- `.ml`d
- `.tk`

#### Record types

This integration can only update A records.
