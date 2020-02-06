Changelog
=========

Version 0.8.0 to 1.0.0-beta

What's Changed
--------------

### \[ Global \]

PATH

> \- Base path turned from `/api/v0` to `/api/v1`

* * *

PATH

_`/devices/{serial}/camera/qualityAndRetentionSettings`_

> \- Deleted

* * *

PATH

_`/devices/{serial}/cellularGateway/settings`_

> \- Deleted

* * *

PATH

_`/devices/{serial}/cellularGateway/settings/portForwardingRules`_

> \- Deleted

* * *

PATH

_`/devices/{serial}/switchPortStatuses`_

> \- Deleted

* * *

PATH

_`/devices/{serial}/switchPortStatuses/packets`_

> \- Deleted

* * *

PATH

_`/networks/{networkId}/appliance/firewall/inboundFirewallRules`_

> \- Deleted

* * *

PATH

_`/networks/{networkId}/camera/qualityRetentionProfiles`_

> \- Deleted

* * *

PATH

_`/networks/{networkId}/camera/qualityRetentionProfiles/{qualityRetentionProfileId}`_

> \- Deleted

* * *

PATH

_`/networks/{networkId}/camera/schedules`_

> \- Deleted

* * *

PATH

_`/networks/{networkId}/cellularGateway/settings/connectivityMonitoringDestinations`_

> \- Deleted

* * *

PATH

_`/networks/{networkId}/cellularGateway/settings/dhcp`_

> \- Deleted

* * *

PATH

_`/networks/{networkId}/cellularGateway/settings/subnetPool`_

> \- Deleted

* * *

PATH

_`/networks/{networkId}/cellularGateway/settings/uplink`_

> \- Deleted

* * *

PATH

_`/networks/{networkId}/switch/linkAggregations`_

> \- Deleted

* * *

PATH

_`/networks/{networkId}/switch/linkAggregations/{linkAggregationId}`_

> \- Deleted

* * *

PATH

_`/networks/{networkId}/switch/settings/multicast`_

> \- Deleted

* * *

PATH

_`/organizations/{organizationId}/insight/monitoredMediaServers`_

> \- Deleted

* * *

PATH

_`/organizations/{organizationId}/insight/monitoredMediaServers/{monitoredMediaServerId}`_

> \- Deleted

* * *

PATH

_`/networks/{networkId}/devices/{serial}`_

> \- renamed to `/devices/{serial}`

* * *

PATH

_`/networks/{networkId}/devices/{serial}/blinkLeds`_

> \- renamed to `/devices/{serial}/blinkLeds`

* * *

PATH

_`/networks/{networkId}/devices/{serial}/lldp_cdp`_

> \- renamed to `/devices/{serial}/lldpCdp`

* * *

PATH

_`/networks/{networkId}/devices/{serial}/lossAndLatencyHistory`_

> \- renamed to `/devices/{serial}/lossAndLatencyHistory`

* * *

PATH

_`/networks/{networkId}/devices/{serial}/performance`_

> \- renamed to `/devices/{serial}/performance`

* * *

PATH

_`/networks/{networkId}/devices/{serial}/reboot`_

> \- renamed to `/devices/{serial}/reboot`

* * *

PATH

_`/networks/{networkId}/devices/{serial}/remove`_

> \- renamed to `/networks/{networkId}/devices/remove`

* * *

PATH

_`/networks/{networkId}/devices/{serial}/uplink`_

> \- renamed to `/devices/{serial}/uplink`

* * *

### \[ Clients \]

[**Provisions a client with a name and policy. Clients can be provisioned before they associate to the network.**](https://developer.cisco.com/meraki/api/#/rest/api-endpoints/clients/provision-network-clients)

POST

_`/networks/{networkId}/clients/provision`_

> \- Property `groupPolicyId` type turn from `integer` to `string`

* * *

### \[ Devices \]

[**Claim a device into a network**](https://developer.cisco.com/meraki/api/#/rest/api-endpoints/devices/claim-network-devices)

POST

_`/networks/{networkId}/devices/claim`_

> \- Property `serial` became required

> \- Param `claimNetworkDevices` became required

* * *

### \[ SSIDs \]

[**Update the attributes of an SSID**](https://developer.cisco.com/meraki/api/#/rest/api-endpoints/ssids/update-network-ssid)

PUT

_`/networks/{networkId}/ssids/{number}`_

> \- Property `walledGardenRanges` type turn from `string` to `array`

* * *

### \[ Networks \]

[**Create a network**](https://developer.cisco.com/meraki/api/#/rest/api-endpoints/networks/create-organization-network)

POST

_`/organizations/{organizationId}/networks`_

> \- Required property `productTypes` added

* * *

What's Updated
--------------

### \[ Devices \]

[**List the devices in an organization**](https://developer.cisco.com/meraki/api/#/rest/api-endpoints/devices/get-organization-devices)

GET

_`/organizations/{organizationId}/devices`_

> \- Param `configurationUpdatedAfter` Deleted

* * *

### \[ Networks \]

[**Create a network**](https://developer.cisco.com/meraki/api/#/rest/api-endpoints/networks/create-organization-network)

POST

_`/organizations/{organizationId}/networks`_

> \- Property `type` Deleted

* * *

[**Combine multiple networks into a single network**](https://developer.cisco.com/meraki/api/#/rest/api-endpoints/networks/combine-organization-networks)

POST

_`/organizations/{organizationId}/networks/combine`_

> \- Property `enrollmentString` Deleted

* * *

[**Update a network**](https://developer.cisco.com/meraki/api/#/rest/api-endpoints/networks/update-network)

PUT

_`/networks/{networkId}`_

> \- Property `enrollmentString` Deleted

* * *

### \[ MX 1:Many NAT rules \]

[**Set the 1:Many NAT mapping rules for an MX network**](https://developer.cisco.com/meraki/api/#/rest/api-endpoints/mx 1:many nat rules/update-network-one-to-many-nat-rules)

PUT

_`/networks/{networkId}/oneToManyNatRules`_

> \- Optional property `name` Added

> \- Optional property `protocol` Added

> \- Optional property `publicPort` Added

> \- Optional property `localIp` Added

> \- Optional property `localPort` Added

> \- Optional property `allowedIps` Added

* * *

### \[ Switch settings \]

[**Update the global enhanced storm control configuration**](https://developer.cisco.com/meraki/api/#/rest/api-endpoints/switch settings/update-network-switch-settings-storm-control)

PUT

_`/networks/{networkId}/switch/settings/stormControl`_

> \- Summary changed from `Update the storm control configuration for a switch network` to `Update the global enhanced storm control configuration`

* * *

[**Return the global enhanced storm control configuration**](https://developer.cisco.com/meraki/api/#/rest/api-endpoints/switch settings/get-network-switch-settings-storm-control)

GET

_`/networks/{networkId}/switch/settings/stormControl`_

> \- Summary changed from `Return the storm control configuration for a switch network` to `Return the global enhanced storm control configuration`

* * *

### \[ Wireless settings \]

[**Update the wireless settings for a network**](https://developer.cisco.com/meraki/api/#/rest/api-endpoints/wireless settings/update-network-wireless-settings)

PUT

_`/networks/{networkId}/wireless/settings`_

> \- Property `ledLightsOn` Deleted

* * *

### \[ Organizations \]

[**Return the device inventory for an organization**](https://developer.cisco.com/meraki/api/#/rest/api-endpoints/organizations/get-organization-inventory)

GET

_`/organizations/{organizationId}/inventory`_

> \- Param `includeLicenseInfo` Deleted

> \- Optional param `perPage` added

> \- Optional param `startingAfter` added

> \- Optional param `endingBefore` added

> \- Response property `orderNumber` value added

> \- Response property `licenseExpirationDate` value added

> \- Response property `headers` value added

> \- Summary changed from `Return the inventory for an organization` to `Return the device inventory for an organization`

* * *

### \[ SM \]

PATH

_`/networks/{networkId}/sm/profile/clarity`_

> \- Path added  
>   
> 
> #### New Endpoint
> 
> **Create a new profile containing a Cisco Clarity payload**
> 
> **POST** `/networks/{networkId}/sm/profile/clarity`  
> 
>     {
>         "success": true,
>         "profile_id": "12345"
>     }

* * *

PATH

_`/networks/{networkId}/sm/profile/clarity/{profileId}`_

> \- Path added  
>   
> 
> #### New Endpoint
> 
> **Get details for a Cisco Clarity payload**
> 
> **GET** `/networks/{networkId}/sm/profile/clarity/{profileId}`  
> 
>     {
>         "profile_id": "12345",
>         "name": "Cisco Clarity Config",
>         "PluginBundleID": "com.cisco.security.app",
>         "FilterBrowsers": true,
>         "FilterSockets": true,
>         "VendorConfig": [
>             {
>                 "key": "cloud_asn1_server_host",
>                 "type": "manual_string",
>                 "value": "immunet.com"
>             },
>             {
>                 "key": "cloud_asn1_server_port",
>                 "type": "manual_int",
>                 "value": 443
>             }
>         ]
>     }
> 
>   
> 
> #### New Endpoint
> 
> **Add a Cisco Clarity payload to an existing profile**
> 
> **POST** `/networks/{networkId}/sm/profile/clarity/{profileId}`  
> 
>     {
>         "success": true,
>         "profile_id": "12345"
>     }
> 
>   
> 
> #### New Endpoint
> 
> **Update an existing profile containing a Cisco Clarity payload**
> 
> **PUT** `/networks/{networkId}/sm/profile/clarity/{profileId}`  
> 
>     {
>         "success": true,
>         "profile_id": "12345"
>     }
> 
>   
> 
> #### New Endpoint
> 
> **Delete a Cisco Clarity payload. Deletes the entire profile if it's empty after removing the payload.**
> 
> **DELETE** `/networks/{networkId}/sm/profile/clarity/{profileId}`  
> 
>     {
>         "success": true,
>         "payload_deleted": true,
>         "profile_deleted": true
>     }

* * *

PATH

_`/networks/{networkId}/sm/profile/umbrella`_

> \- Path added  
>   
> 
> #### New Endpoint
> 
> **Create a new profile containing a Cisco Umbrella payload**
> 
> **POST** `/networks/{networkId}/sm/profile/umbrella`  
> 
>     {
>         "success": true,
>         "profile_id": "12345"
>     }

* * *

PATH

_`/networks/{networkId}/sm/profile/umbrella/{profileId}`_

> \- Path added  
>   
> 
> #### New Endpoint
> 
> **Get details for a Cisco Umbrella payload**
> 
> **GET** `/networks/{networkId}/sm/profile/umbrella/{profileId}`  
> 
>     {
>         "profile_id": "12345",
>         "name": "Cisco Umbrella Config",
>         "AppBundleIdentifier": "com.cisco.security",
>         "ProviderBundleIdentifier": "com.cisco.umbrella",
>         "ProviderConfiguration": [
>             {
>                 "key": "internalDomains",
>                 "type": "manual_list",
>                 "value": [
>                     "meraki.com",
>                     "cisco.com"
>                 ]
>             },
>             {
>                 "key": "user_id",
>                 "type": "manual_string",
>                 "value": "miles"
>             }
>         ]
>     }
> 
>   
> 
> #### New Endpoint
> 
> **Add a Cisco Umbrella payload to an existing profile**
> 
> **POST** `/networks/{networkId}/sm/profile/umbrella/{profileId}`  
> 
>     {
>         "success": true,
>         "profile_id": "12345"
>     }
> 
>   
> 
> #### New Endpoint
> 
> **Update an existing profile containing a Cisco Umbrella payload**
> 
> **PUT** `/networks/{networkId}/sm/profile/umbrella/{profileId}`  
> 
>     {
>         "success": true,
>         "profile_id": "12345"
>     }
> 
>   
> 
> #### New Endpoint
> 
> **Delete a Cisco Umbrella payload. Deletes the entire profile if it's empty after removing the payload**
> 
> **DELETE** `/networks/{networkId}/sm/profile/umbrella/{profileId}`  
> 
>     {
>         "success": true,
>         "payload_deleted": true,
>         "profile_deleted": true
>     }

* * *