Meraki Dashboard API Changelog

Changelog
=========

Version 0.5.0 to 0.0.0-alpha

Changes
-------

#### PATH

> Host turned from `api.meraki.com` to `api-mp.meraki.com`

* * *

### Group policies

**Create a group policy**

#### POST

`/networks/{networkId}/groupPolicies`

> **Required property** `srcCidr` Added

> Optional property `srcPort` Added

* * *

**Update a group policy**

#### PUT

`/networks/{networkId}/groupPolicies/{groupPolicyId}`

> **Required property** `srcCidr` Added

> Optional property `srcPort` Added

* * *

### SAML roles

**Create a SAML role**

#### POST

`/organizations/{organizationId}/samlRoles`

> Response `200` Deleted

> Response property `201` value added:
> 
>            
>             {
>               201: {"description":"Successful operation","schema":{"type":"object","x-is-dynamic":true},"examples":{"application/json":{"id":"TEdJIEN1c3RvbWVy","role":"myrole","orgAccess":"none","networks":[{"id":"N_1234","access":"full"}],"tags":[{"tag":"west","access":"read-only"}]}}}
>             }
>     

* * *

### Switch ports

**Update a switch port**

#### PUT

`/devices/{serial}/switchPorts/{number}`

> Optional property `stormControlEnabled` Added

* * *

**List the switch ports for a switch**

#### GET

`/devices/{serial}/switchPorts`

> Response property `macWhitelist` value added:
> 
>            
>             {
>               macWhitelist: ["34:56:fe:ce:8e:a0","34:56:fe:ce:8e:a1"]
>             }
>     

> Response property `stormControlEnabled` value added:
> 
>            
>             {
>               stormControlEnabled: true
>             }
>     

* * *

**Return a switch port**

#### GET

`/devices/{serial}/switchPorts/{number}`

> Response property `macWhitelist` value added:
> 
>            
>             {
>               macWhitelist: ["34:56:fe:ce:8e:a0","34:56:fe:ce:8e:a1"]
>             }
>     

> Response property `stormControlEnabled` value added:
> 
>            
>             {
>               stormControlEnabled: true
>             }
>     

* * *

### Networks

**Combine multiple networks into a single network**

#### POST

`/organizations/{organizationId}/networks/combine`

> Optional property `enrollmentString` Added

* * *

**Update a network**

#### PUT

`/networks/{networkId}`

> Optional property `enrollmentString` Added

* * *

**Return a network**

#### GET

`/networks/{networkId}`

> Response property `enrollmentString` value added:
> 
>            
>             {
>               enrollmentString: "long-island-office"
>             }
>     

* * *

**List the networks in an organization**

#### GET

`/organizations/{organizationId}/networks`

> Response property `enrollmentString` value added:
> 
>            
>             {
>               enrollmentString: "long-island-office"
>             }
>     

* * *

### SM

#### PATH

`/networks/{networkId}/sm/device/{deviceId}/installApps`

> Path added  
> 
> POST
> 
> _installNetworkSmDeviceApps_  
> **Install applications on a device**

* * *

#### PATH

`/networks/{networkId}/sm/device/{deviceId}/uninstallApps`

> Path added  
> 
> POST
> 
> _uninstallNetworkSmDeviceApps_  
> **Uninstall applications on a device**

* * *

**Get a list of softwares associated with a user**

#### GET

`/networks/{networkId}/sm/user/{userId}/softwares`

> Response property `appId` value added:
> 
>            
>             {
>               appId: "1234"
>             }
>     

* * *

**Get a list of softwares associated with a device**

#### GET

`/networks/{networkId}/sm/{deviceId}/softwares`

> Response property `appId` value added:
> 
>            
>             {
>               appId: "1234"
>             }
>     

* * *

### API usage

**List the API requests made by an organization**

#### GET

`/organizations/{organizationId}/apiRequests`

> Optional param `sourceIp` added

> Response property `sourceIp` value added:
> 
>            
>             {
>               sourceIp: "123.123.123.1"
>             }
>     

* * *

### Devices

**List the devices in an organization**

#### GET

`/organizations/{organizationId}/devices`

> Optional param `configurationUpdatedAfter` added

* * *

### Organizations

**Update the third party VPN peers for an organization**

#### PUT

`/organizations/{organizationId}/thirdPartyVPNPeers`

> Optional property `remoteId` Added

* * *

**Return the inventory for an organization**

#### GET

`/organizations/{organizationId}/inventory`

> Optional param `includeLicenseInfo` added

* * *

**Return the third party VPN peers for an organization**

#### GET

`/organizations/{organizationId}/thirdPartyVPNPeers`

> Response property `remoteId` value added:
> 
>            
>             {
>               remoteId: "miles@meraki.com"
>             }
>     

* * *

### Cameras

#### PATH

`/devices/{serial}/camera/qualityAndRetentionSettings`

> Path added  
> 
> GET
> 
> _getDeviceCameraQualityAndRetentionSettings_  
> **Returns quality and retention settings for the given camera**
> 
>     {
>         "motionBasedRetentionEnabled": false,
>         "audioRecordingEnabled": false,
>         "restrictedBandwidthModeEnabled": false,
>         "profileId": null,
>         "quality": "Standard",
>         "resolution": 720
>     }
> 
>   
> 
> PUT
> 
> _updateDeviceCameraQualityAndRetentionSettings_  
> **Update quality and retention settings for the given camera**
> 
>     {
>         "motionBasedRetentionEnabled": false,
>         "audioRecordingEnabled": false,
>         "restrictedBandwidthModeEnabled": false,
>         "profileId": null,
>         "quality": "Standard",
>         "resolution": 720
>     }

* * *

### MG LAN Settings

#### PATH

`/devices/{serial}/cellularGateway/settings`

> Path added  
> 
> GET
> 
> _getDeviceCellularGatewaySettings_  
> **Show the LAN Settings of a MG**
> 
>     {
>         "deviceName": "name of the MG",
>         "deviceLanIp": "",
>         "deviceSubnet": "",
>         "fixedIpAssignments": [
>             {
>                 "mac": "0b:00:00:00:00:ac",
>                 "name": "server 1",
>                 "ip": "192.168.0.10"
>             },
>             {
>                 "mac": "0b:00:00:00:00:ab",
>                 "name": "server 2",
>                 "ip": "192.168.0.20"
>             }
>         ],
>         "reservedIpRanges": [
>             {
>                 "start": "192.168.1.0",
>                 "end": "192.168.1.1",
>                 "comment": "A reserved IP range"
>             }
>         ]
>     }
> 
>   
> 
> PUT
> 
> _updateDeviceCellularGatewaySettings_  
> **Update the LAN Settings for a single MG.**
> 
>     {
>         "deviceName": "name of the MG",
>         "deviceLanIp": "",
>         "deviceSubnet": "",
>         "fixedIpAssignments": [
>             {
>                 "mac": "0b:00:00:00:00:ac",
>                 "name": "server 1",
>                 "ip": "192.168.0.10"
>             },
>             {
>                 "mac": "0b:00:00:00:00:ab",
>                 "name": "server 2",
>                 "ip": "192.168.0.20"
>             }
>         ],
>         "reservedIpRanges": [
>             {
>                 "start": "192.168.1.0",
>                 "end": "192.168.1.1",
>                 "comment": "A reserved IP range"
>             }
>         ]
>     }

* * *

### MGs DHCP settings

#### PATH

`/networks/{networkId}/cellularGateway/dhcpSettings`

> Path added  
> 
> GET
> 
> _getNetworkCellularGatewayDhcpSettings_  
> **List common DHCP settings of MGs**
> 
>     {
>         "dhcpLeaseTime": "1 hour",
>         "dnsNameserversMode": "custom",
>         "dnsCustomNameservers": [
>             "172.16.2.111",
>             "172.16.2.30"
>         ]
>     }
> 
>   
> 
> PUT
> 
> _updateNetworkCellularGatewayDhcpSettings_  
> **Update common DHCP settings of MGs**
> 
>     {
>         "dhcpLeaseTime": "1 hour",
>         "dnsNameserversMode": "custom",
>         "dnsCustomNameservers": [
>             "172.16.2.111",
>             "172.16.2.30"
>         ]
>     }

* * *

### Clients

#### PATH

`/networks/{networkId}/clients/countHistory`

> Path added  
> 
> GET
> 
> _getNetworkClientsCountHistory_  
> **Return a time series of client counts for the network. This endpoint is only available for networks on MR 27.0 or above.**
> 
>     [
>         {
>             "startTs": 1518365681,
>             "endTs": 1526087474,
>             "clientCount": 39
>         }
>     ]

* * *

### Cellular uplink configurations

#### PATH

`/networks/{networkId}/devices/{serial}/uplink/cellular`

> Path added  
> 
> GET
> 
> _getNetworkDeviceUplinkCellular_  
> **Return the cellular uplink configurations for a device.**
> 
>     [
>         [
>             {
>                 "enabled": true,
>                 "apn": "my.apn",
>                 "id": "rg5xBa"
>             }
>         ]
>     ]
> 
>   
> 
> POST
> 
> _createNetworkDeviceUplinkCellular_  
> **Create an uplink configuration for a device.**
> 
>     {
>         "apn": "my.apn",
>         "enabled": true
>     }

* * *

#### PATH

`/networks/{networkId}/devices/{serial}/uplink/cellular/{id}`

> Path added  
> 
> GET
> 
> _getNetworkDeviceUplinkCellular_  
> **Return the cellular uplink configuration.**
> 
>     {
>         "apn": "my.apn",
>         "enabled": true
>     }
> 
>   
> 
> PUT
> 
> _updateNetworkDeviceUplinkCellular_  
> **Update cellular uplink configuration**
> 
>     {
>         "apn": "my.apn",
>         "enabled": true
>     }

* * *

### Network health

#### PATH

`/networks/{networkId}/networkHealth/channelUtilization`

> Path added  
> 
> GET
> 
> _getNetworkNetworkHealthChannelUtilization_  
> **Get the channel utilization over each radio for all APs in a network.**
> 
>     [
>         {
>             "serial": "Q234-ABCD-5678",
>             "model": "MR34",
>             "tags": " recently-added ",
>             "wifi0": [
>                 {
>                     "startTime": "2018-10-09T22:18:27Z",
>                     "endTime": "2018-10-09T22:19:27Z",
>                     "utilizationTotal": 33.84,
>                     "utilization80211": 32,
>                     "utilizationNon80211": 1.84
>                 },
>                 {
>                     "startTime": "2018-10-09T22:19:27Z",
>                     "endTime": "2018-10-09T22:20:27Z",
>                     "utilizationTotal": 33.85,
>                     "utilization80211": 32.01,
>                     "utilizationNon80211": 1.84
>                 },
>                 {
>                     "startTime": "2018-10-09T22:20:27Z",
>                     "endTime": "2018-10-09T22:21:27Z",
>                     "utilizationTotal": 34.89,
>                     "utilization80211": 33.48,
>                     "utilizationNon80211": 1.41
>                 }
>             ],
>             "wifi1": [
>                 {
>                     "startTime": "2018-10-09T22:18:27Z",
>                     "endTime": "2018-10-09T22:19:27Z",
>                     "utilizationTotal": 33.84,
>                     "utilization80211": 32,
>                     "utilizationNon80211": 1.84
>                 },
>                 {
>                     "startTime": "2018-10-09T22:19:27Z",
>                     "endTime": "2018-10-09T22:20:27Z",
>                     "utilizationTotal": 33.85,
>                     "utilization80211": 32.01,
>                     "utilizationNon80211": 1.84
>                 },
>                 {
>                     "startTime": "2018-10-09T22:20:27Z",
>                     "endTime": "2018-10-09T22:21:27Z",
>                     "utilizationTotal": 34.89,
>                     "utilization80211": 33.48,
>                     "utilizationNon80211": 1.41
>                 }
>             ]
>         }
>     ]

* * *

### Sensors

#### PATH

`/networks/{networkId}/sensors`

> Path added  
> 
> GET
> 
> _getNetworkSensors_  
> **List all sensors in a given network.**
> 
>     [
>         {
>             "serial": "Q234-ABCD-5678",
>             "name": "My sensor",
>             "alertProfiles": [
>                 "HVAC"
>             ]
>         }
>     ]

* * *

### Apps

#### PATH

`/networks/{networkId}/sm/apps`

> Path added  
> 
> GET
> 
> _getNetworkSmApps_  
> **List the managed apps for this network**
> 
>     [
>         {
>             "id": "1234",
>             "networkId": "N_24329156",
>             "name": "My managed app",
>             "identifier": "com.test.app",
>             "systemType": "ios",
>             "installMethod": "store",
>             "vendor": "App Developer Inc.",
>             "version": "1.2.3",
>             "itunesId": "472572197",
>             "description": "Some app description",
>             "purchaseMethod": "vppDeviceAssignment",
>             "scope": "all",
>             "tags": "[]",
>             "autoInstall": true,
>             "autoUpdate": true,
>             "removeWithMdm": false,
>             "attemptToManage": true,
>             "backupOnSync": true
>         }
>     ]
> 
>   
> 
> POST
> 
> _createNetworkSmApp_  
> **Add a managed app**
> 
>     {
>         "id": "1234",
>         "networkId": "N_24329156",
>         "name": "My managed app",
>         "identifier": "com.test.app",
>         "systemType": "ios",
>         "installMethod": "store",
>         "vendor": "App Developer Inc.",
>         "version": "1.2.3",
>         "itunesId": "472572197",
>         "description": "Some app description",
>         "purchaseMethod": "vppDeviceAssignment",
>         "scope": "all",
>         "tags": "[]",
>         "autoInstall": true,
>         "autoUpdate": true,
>         "removeWithMdm": false,
>         "attemptToManage": true,
>         "backupOnSync": true
>     }

* * *

#### PATH

`/networks/{networkId}/sm/apps/{appId}`

> Path added  
> 
> GET
> 
> _getNetworkSmApp_  
> **Return a managed app**
> 
>     {
>         "id": "1234",
>         "networkId": "N_24329156",
>         "name": "My managed app",
>         "identifier": "com.test.app",
>         "systemType": "ios",
>         "installMethod": "store",
>         "vendor": "App Developer Inc.",
>         "version": "1.2.3",
>         "itunesId": "472572197",
>         "description": "Some app description",
>         "purchaseMethod": "vppDeviceAssignment",
>         "scope": "all",
>         "tags": "[]",
>         "autoInstall": true,
>         "autoUpdate": true,
>         "removeWithMdm": false,
>         "attemptToManage": true,
>         "backupOnSync": true
>     }
> 
>   
> 
> PUT
> 
> _updateNetworkSmApp_  
> **Update a managed app**
> 
>     {
>         "id": "1234",
>         "networkId": "N_24329156",
>         "name": "My managed app",
>         "identifier": "com.test.app",
>         "systemType": "ios",
>         "installMethod": "store",
>         "vendor": "App Developer Inc.",
>         "version": "1.2.3",
>         "itunesId": "472572197",
>         "description": "Some app description",
>         "purchaseMethod": "vppDeviceAssignment",
>         "scope": "all",
>         "tags": "[]",
>         "autoInstall": true,
>         "autoUpdate": true,
>         "removeWithMdm": false,
>         "attemptToManage": true,
>         "backupOnSync": true
>     }
> 
>   
> 
> DELETE
> 
> _deleteNetworkSmApp_  
> **Delete a managed app from a network**

* * *

### Geofences

#### PATH

`/networks/{networkId}/sm/geofences`

> Path added  
> 
> GET
> 
> _getNetworkSmGeofences_  
> **List the geofences in this network**
> 
>     [
>         {
>             "name": "My Geofence",
>             "description": "This is a sample geofence",
>             "maxTimeOutside": 5
>         }
>     ]
> 
>   
> 
> POST
> 
> _createNetworkSmGeofence_  
> **Add a new geofence**
> 
>     {
>         "name": "My Geofence",
>         "description": "This is a sample geofence",
>         "maxTimeOutside": 5
>     }

* * *

#### PATH

`/networks/{networkId}/sm/geofences/{geofenceId}`

> Path added  
> 
> GET
> 
> _getNetworkSmGeofence_  
> **Returns a specific geofence**
> 
>     {
>         "name": "My Geofence",
>         "description": "This is a sample geofence",
>         "maxTimeOutside": 5
>     }
> 
>   
> 
> PUT
> 
> _updateNetworkSmGeofence_  
> **Update a geofence**
> 
>     {
>         "name": "My Geofence",
>         "description": "This is a sample geofence",
>         "maxTimeOutside": 5
>     }
> 
>   
> 
> DELETE
> 
> _deleteNetworkSmGeofence_  
> **Delete a geofence**

* * *

### Geofence regions

#### PATH

`/networks/{networkId}/sm/geofences/{geofenceId}/regions`

> Path added  
> 
> GET
> 
> _getNetworkSmGeofenceRegions_  
> **List the geofence's regions associated with the specified geofence**
> 
>     [
>         {
>             "description": "This is a sample geofence region",
>             "type": "circle",
>             "lat": 10,
>             "lng": 10,
>             "radius": 10
>         }
>     ]
> 
>   
> 
> POST
> 
> _createNetworkSmGeofenceRegion_  
> **Add a new geofence region to the specified geofence**
> 
>     {
>         "description": "This is a sample geofence region",
>         "type": "circle",
>         "lat": 10,
>         "lng": 10,
>         "radius": 10
>     }

* * *

#### PATH

`/networks/{networkId}/sm/geofences/{geofenceId}/regions/{regionId}`

> Path added  
> 
> GET
> 
> _getNetworkSmGeofenceRegion_  
> **Show the specified geofence region**
> 
>     {
>         "description": "This is a sample geofence region",
>         "type": "circle",
>         "lat": 10,
>         "lng": 10,
>         "radius": 10
>     }
> 
>   
> 
> PUT
> 
> _updateNetworkSmGeofenceRegion_  
> **Update a specified geofence region**
> 
>     {
>         "description": "This is a sample geofence region",
>         "type": "circle",
>         "lat": 10,
>         "lng": 10,
>         "radius": 10
>     }
> 
>   
> 
> DELETE
> 
> _deleteNetworkSmGeofenceRegion_  
> **Delete a geofence region attached to the specified geofence**

* * *

### Tags

#### PATH

`/networks/{networkId}/sm/tags`

> Path added  
> 
> GET
> 
> _getNetworkSmTags_  
> **List the tags on this node group**
> 
>     [
>         {
>             "name": "Geofence Tag",
>             "type": "geofence",
>             "scope": "withAll",
>             "tags": [
>                 "tag",
>                 "test"
>             ]
>         }
>     ]
> 
>   
> 
> POST
> 
> _createNetworkSmTag_  
> **Add a new tag**
> 
>     {
>         "name": "Geofence Tag",
>         "type": "geofence",
>         "scope": "withAll",
>         "tags": [
>             "tag",
>             "test"
>         ]
>     }

* * *

#### PATH

`/networks/{networkId}/sm/tags/{tagId}`

> Path added  
> 
> GET
> 
> _getNetworkSmTag_  
> **Show a specific tag**
> 
>     {
>         "name": "Geofence Tag",
>         "type": "geofence",
>         "scope": "withAll",
>         "tags": [
>             "tag",
>             "test"
>         ]
>     }
> 
>   
> 
> PUT
> 
> _updateNetworkSmTag_  
> **Update a tag**
> 
>     {
>         "name": "Geofence Tag",
>         "type": "geofence",
>         "scope": "withAll",
>         "tags": [
>             "tag",
>             "test"
>         ]
>     }
> 
>   
> 
> DELETE
> 
> _deleteNetworkSmTag_  
> **Delete a tag**

* * *

#### PATH

`/networks/{networkId}/sm/tags/{tagId}/scopedDevices`

> Path added  
> 
> GET
> 
> _getNetworkSmTagScopedDevices_  
> **Get the devices in scope of this tag**
> 
>     [
>         {
>             "name": "Geofence Tag",
>             "type": "geofence",
>             "scope": "withAll",
>             "tags": [
>                 "tag",
>                 "test"
>             ]
>         }
>     ]

* * *

### SSIDs

#### PATH

`/networks/{networkId}/ssids/{number}/reset`

> Path added  
> 
> POST
> 
> _resetNetworkSsid_  
> **Reset configuration and stats for an SSID**
> 
>     {
>         "number": 0,
>         "name": "My SSID",
>         "enabled": true,
>         "splashPage": "Click-through splash page",
>         "ssidAdminAccessible": false,
>         "authMode": "8021x-radius",
>         "encryptionMode": "wpa-eap",
>         "wpaEncryptionMode": "WPA2 only",
>         "radiusServers": [
>             {
>                 "host": "0.0.0.0",
>                 "port": 3000
>             }
>         ],
>         "radiusAccountingEnabled": false,
>         "radiusEnabled": true,
>         "radiusAttributeForGroupPolicies": "Filter-Id",
>         "radiusFailoverPolicy": "null",
>         "radiusLoadBalancingPolicy": "null",
>         "ipAssignmentMode": "NAT mode",
>         "adminSplashUrl": "http://example.com",
>         "splashTimeout": "30 minutes",
>         "walledGardenEnabled": true,
>         "walledGardenRanges": "example.com",
>         "minBitrate": 11,
>         "bandSelection": "5 GHz band only",
>         "perClientBandwidthLimitUp": 0,
>         "perClientBandwidthLimitDown": 0
>     }

* * *

### Switch ACLs

#### PATH

`/networks/{networkId}/switch/accessControlLists`

> Path added  
> 
> GET
> 
> _getNetworkSwitchAccessControlLists_  
> **Return the access control lists for a MS network**
> 
>     {
>         "rules": [
>             {
>                 "comment": "Deny SSH",
>                 "policy": "deny",
>                 "ipVersion": "ipv4",
>                 "protocol": "tcp",
>                 "srcCidr": "10.1.10.0/24",
>                 "srcPort": "any",
>                 "dstCidr": "172.16.30/24",
>                 "dstPort": 22,
>                 "vlan": 10
>             },
>             {
>                 "comment": "Default rule",
>                 "policy": "allow",
>                 "ipVersion": "any",
>                 "protocol": "any",
>                 "srcCidr": "any",
>                 "srcPort": "any",
>                 "dstCidr": "any",
>                 "dstPort": "any",
>                 "vlan": "any"
>             }
>         ]
>     }
> 
>   
> 
> PUT
> 
> _updateNetworkSwitchAccessControlLists_  
> **Update the access control lists for a MS network**
> 
>     {
>         "rules": [
>             {
>                 "comment": "Deny SSH",
>                 "policy": "deny",
>                 "ipVersion": "ipv4",
>                 "protocol": "tcp",
>                 "srcCidr": "10.1.10.0/24",
>                 "srcPort": "any",
>                 "dstCidr": "172.16.30/24",
>                 "dstPort": 22,
>                 "vlan": 10
>             },
>             {
>                 "comment": "Default rule",
>                 "policy": "allow",
>                 "ipVersion": "any",
>                 "protocol": "any",
>                 "srcCidr": "any",
>                 "srcPort": "any",
>                 "dstCidr": "any",
>                 "dstPort": "any",
>                 "vlan": "any"
>             }
>         ]
>     }

* * *

### Switch settings

#### PATH

`/networks/{networkId}/switch/settings/dhcpServerPolicy`

> Path added  
> 
> GET
> 
> _getNetworkSwitchSettingsDhcpServerPolicy_  
> **Return the DHCP server policy**
> 
>     {
>         "defaultPolicy": "block",
>         "allowedServers": [
>             "00:50:56:00:00:01",
>             "00:50:56:00:00:02"
>         ]
>     }
> 
>   
> 
> PUT
> 
> _updateNetworkSwitchSettingsDhcpServerPolicy_  
> **Update the DHCP server policy**
> 
>     {
>         "defaultPolicy": "block",
>         "allowedServers": [
>             "00:50:56:00:00:01",
>             "00:50:56:00:00:02"
>         ]
>     }

* * *

#### PATH

`/networks/{networkId}/switch/settings/dscpToCosMappings`

> Path added  
> 
> GET
> 
> _getNetworkSwitchSettingsDscpToCosMappings_  
> **Return the DSCP to CoS mappings**
> 
>     {
>         "mappings": [
>             {
>                 "dscp": 1,
>                 "cos": 1,
>                 "title": "Video"
>             }
>         ]
>     }
> 
>   
> 
> PUT
> 
> _updateNetworkSwitchSettingsDscpToCosMappings_  
> **Update the DSCP to CoS mappings**
> 
>     {
>         "mappings": [
>             {
>                 "dscp": 1,
>                 "cos": 1,
>                 "title": "Video"
>             }
>         ]
>     }

* * *

### Organization alert settings

#### PATH

`/organizations/{organizationId}/alertSettings`

> Path added  
> 
> GET
> 
> _getOrganizationAlertSettings_  
> **Return the alert configuration for this organization**
> 
>     {
>         "defaultDestinations": {
>             "emails": [
>                 "miles@meraki.com"
>             ],
>             "allAdmins": true
>         },
>         "alerts": [
>             {
>                 "type": "insightAppOutage",
>                 "enabled": true,
>                 "alertDestinations": {
>                     "emails": [
>                         "miles@meraki.com"
>                     ],
>                     "allAdmins": false
>                 },
>                 "filters": {
>                     "alertOnAllApps": true
>                 }
>             }
>         ]
>     }
> 
>   
> 
> PUT
> 
> _updateOrganizationAlertSettings_  
> **Update the alert configuration for this organization**
> 
>     {
>         "defaultDestinations": {
>             "emails": [
>                 "miles@meraki.com"
>             ],
>             "allAdmins": true
>         },
>         "alerts": [
>             {
>                 "type": "insightAppOutage",
>                 "enabled": true,
>                 "alertDestinations": {
>                     "emails": [
>                         "miles@meraki.com"
>                     ],
>                     "allAdmins": false
>                 },
>                 "filters": {
>                     "alertOnAllApps": true
>                 }
>             }
>         ]
>     }

* * *

### Licenses

#### PATH

`/organizations/{organizationId}/licenses`

> Path added  
> 
> GET
> 
> _getOrganizationLicenses_  
> **List the licenses for an organization**
> 
>     [
>         {
>             "id": "1234",
>             "licenseType": "MX64-ENT",
>             "licenseKey": "Z21234567890",
>             "orderNumber": "4C1234567",
>             "deviceSerial": "Q234-ABCD-5678",
>             "networkId": "N_24329156",
>             "state": "active",
>             "seatCount": null,
>             "totalDurationInDays": 425,
>             "durationInDays": 365,
>             "permanentlyQueuedLicenses": [
>                 {
>                     "id": "5678",
>                     "licenseType": "MX64-ENT",
>                     "licenseKey": "Z21234567890",
>                     "orderNumber": "4C1234567",
>                     "durationInDays": 60
>                 }
>             ],
>             "claimDate": "2019-08-29T12:40:10Z",
>             "activationDate": "2019-09-01T15:01:46Z",
>             "expirationDate": "2020-10-30T15:01:46Z"
>         }
>     ]

* * *

#### PATH

`/organizations/{organizationId}/licenses/assignSeats`

> Path added  
> 
> POST
> 
> _assignOrganizationLicensesSeats_  
> **Assign SM seats to a network. This will increase the managed SM device limit of the network**
> 
>     {
>         "resultingLicenses": [
>             {
>                 "id": "1234",
>                 "licenseType": "SME",
>                 "licenseKey": "Z21234567890",
>                 "orderNumber": "4C1234567",
>                 "deviceSerial": null,
>                 "networkId": "N_24329156",
>                 "state": "active",
>                 "seatCount": 25,
>                 "totalDurationInDays": 365,
>                 "durationInDays": 365,
>                 "permanentlyQueuedLicenses": [],
>                 "claimDate": "2019-08-29T12:40:10Z",
>                 "activationDate": "2019-09-01T15:01:46Z",
>                 "expirationDate": "2020-08-31T15:01:46Z"
>             }
>         ]
>     }

* * *

#### PATH

`/organizations/{organizationId}/licenses/move`

> Path added  
> 
> POST
> 
> _moveOrganizationLicenses_  
> **Move licenses to another organization. This will also move any devices that the licenses are assigned to**
> 
>     {
>         "destOrganizationId": "2930418",
>         "licenseIds": [
>             "123",
>             "456"
>         ]
>     }

* * *

#### PATH

`/organizations/{organizationId}/licenses/moveSeats`

> Path added  
> 
> POST
> 
> _moveOrganizationLicensesSeats_  
> **Move SM seats to another organization**
> 
>     {
>         "destOrganizationId": "2930418",
>         "licenseId": "1234",
>         "seatCount": 20
>     }

* * *

#### PATH

`/organizations/{organizationId}/licenses/renewSeats`

> Path added  
> 
> POST
> 
> _renewOrganizationLicensesSeats_  
> **Renew SM seats of a license. This will extend the license expiration date of managed SM devices covered by this license**
> 
>     {
>         "resultingLicenses": [
>             {
>                 "id": "1234",
>                 "licenseType": "SME",
>                 "licenseKey": "Z21234567890",
>                 "orderNumber": "4C1234567",
>                 "deviceSerial": null,
>                 "networkId": "N_24329156",
>                 "state": "active",
>                 "seatCount": 25,
>                 "totalDurationInDays": 365,
>                 "durationInDays": 365,
>                 "permanentlyQueuedLicenses": [],
>                 "claimDate": "2019-08-29T12:40:10Z",
>                 "activationDate": "2019-09-01T15:01:46Z",
>                 "expirationDate": "2020-08-31T15:01:46Z"
>             }
>         ]
>     }

* * *

#### PATH

`/organizations/{organizationId}/licenses/{licenseId}`

> Path added  
> 
> GET
> 
> _getOrganizationLicense_  
> **Display a license**
> 
>     {
>         "id": "1234",
>         "licenseType": "MX64-ENT",
>         "licenseKey": "Z21234567890",
>         "orderNumber": "4C1234567",
>         "deviceSerial": "Q234-ABCD-5678",
>         "networkId": "N_24329156",
>         "state": "active",
>         "seatCount": null,
>         "totalDurationInDays": 425,
>         "durationInDays": 365,
>         "permanentlyQueuedLicenses": [
>             {
>                 "id": "5678",
>                 "licenseType": "MX64-ENT",
>                 "licenseKey": "Z21234567890",
>                 "orderNumber": "4C1234567",
>                 "durationInDays": 60
>             }
>         ],
>         "claimDate": "2019-08-29T12:40:10Z",
>         "activationDate": "2019-09-01T15:01:46Z",
>         "expirationDate": "2020-10-30T15:01:46Z"
>     }
> 
>   
> 
> PUT
> 
> _updateOrganizationLicense_  
> **Update a license**
> 
>     {
>         "id": "1234",
>         "licenseType": "MX64-ENT",
>         "licenseKey": "Z21234567890",
>         "orderNumber": "4C1234567",
>         "deviceSerial": "Q234-ABCD-5678",
>         "networkId": "N_24329156",
>         "state": "active",
>         "seatCount": null,
>         "totalDurationInDays": 425,
>         "durationInDays": 365,
>         "permanentlyQueuedLicenses": [
>             {
>                 "id": "5678",
>                 "licenseType": "MX64-ENT",
>                 "licenseKey": "Z21234567890",
>                 "orderNumber": "4C1234567",
>                 "durationInDays": 60
>             }
>         ],
>         "claimDate": "2019-08-29T12:40:10Z",
>         "activationDate": "2019-09-01T15:01:46Z",
>         "expirationDate": "2020-10-30T15:01:46Z"
>     }

* * *

### Users

#### PATH

`/organizations/{organizationId}/users`

> Path added  
> 
> GET
> 
> _getOrganizationUsers_  
> **List the users in an organization**
> 
>     [
>         {
>             "email": "miles@meraki.com",
>             "fullName": "Miles Meraki",
>             "tags": "meraki contractor dayUse",
>             "sources": [
>                 "systemsManager",
>                 "activeDirectory"
>             ],
>             "authData": {
>                 "systemsManager": [
>                     {
>                         "networkId": "N_12345",
>                         "id": "11111"
>                     }
>                 ],
>                 "activeDirectory": [
>                     {
>                         "networkId": "N_34567",
>                         "id": "1"
>                     },
>                     {
>                         "networkId": "N_23456",
>                         "id": "1"
>                     }
>                 ]
>             },
>             "policies": [
>                 {
>                     "networkId": "N_12345",
>                     "sspEnabled": "true"
>                 },
>                 {
>                     "networkId": "N_34567",
>                     "sspEnabled": "true",
>                     "trustedAccessEnabled": "true",
>                     "policyIds": [
>                         "11111",
>                         "9999999"
>                     ]
>                 }
>             ],
>             "devices": [
>                 {
>                     "type": "managed",
>                     "id": "12345",
>                     "networkId": "N_12345"
>                 },
>                 {
>                     "type": "trusted",
>                     "id": "12345",
>                     "networkId": "N_34567"
>                 }
>             ]
>         }
>     ]
> 
>   
> 
> POST
> 
> _createOrganizationUser_  
> **Create a single network end user**
> 
>     {
>         "email": "miles@meraki.com",
>         "fullName": "Miles Meraki",
>         "tags": "meraki contractor dayUse",
>         "sources": [
>             "systemsManager",
>             "activeDirectory"
>         ],
>         "authData": {
>             "systemsManager": [
>                 {
>                     "networkId": "N_12345",
>                     "id": "11111"
>                 }
>             ],
>             "activeDirectory": [
>                 {
>                     "networkId": "N_34567",
>                     "id": "1"
>                 },
>                 {
>                     "networkId": "N_23456",
>                     "id": "1"
>                 }
>             ]
>         },
>         "policies": [
>             {
>                 "networkId": "N_12345",
>                 "sspEnabled": "true"
>             },
>             {
>                 "networkId": "N_34567",
>                 "sspEnabled": "true",
>                 "trustedAccessEnabled": "true",
>                 "policyIds": [
>                     "11111",
>                     "9999999"
>                 ]
>             }
>         ],
>         "devices": [
>             {
>                 "type": "managed",
>                 "id": "12345",
>                 "networkId": "N_12345"
>             },
>             {
>                 "type": "trusted",
>                 "id": "12345",
>                 "networkId": "N_34567"
>             }
>         ]
>     }
> 
>   
> 
> DELETE
> 
> _deleteOrganizationUsers_  
> **Delete a single Meraki managed end user**

* * *

#### PATH

`/organizations/{organizationId}/users/detail`

> Path added  
> 
> GET
> 
> _getOrganizationUsersDetail_  
> **Return a single network end user**
> 
>     {
>         "email": "miles@meraki.com",
>         "fullName": "Miles Meraki",
>         "tags": "meraki contractor dayUse",
>         "sources": [
>             "systemsManager",
>             "activeDirectory"
>         ],
>         "authData": {
>             "systemsManager": [
>                 {
>                     "networkId": "N_12345",
>                     "id": "11111"
>                 }
>             ],
>             "activeDirectory": [
>                 {
>                     "networkId": "N_34567",
>                     "id": "1"
>                 },
>                 {
>                     "networkId": "N_23456",
>                     "id": "1"
>                 }
>             ]
>         },
>         "policies": [
>             {
>                 "networkId": "N_12345",
>                 "sspEnabled": "true"
>             },
>             {
>                 "networkId": "N_34567",
>                 "sspEnabled": "true",
>                 "trustedAccessEnabled": "true",
>                 "policyIds": [
>                     "11111",
>                     "9999999"
>                 ]
>             }
>         ],
>         "devices": [
>             {
>                 "type": "managed",
>                 "id": "12345",
>                 "networkId": "N_12345"
>             },
>             {
>                 "type": "trusted",
>                 "id": "12345",
>                 "networkId": "N_34567"
>             }
>         ]
>     }

* * *

Renamed
-------

#### PATH

`/organizations/{organizationId}/samlRoles/{id}`

> Path `/organizations/{organizationId}/samlRoles/{id}` renamed to `/organizations/{organizationId}/samlRoles/{samlRoleId}`

* * *