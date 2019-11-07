Meraki Dashboard API Changelog

# Changelog

Version 0.0.0 to 1.0.0 (streaming)

## Major

#### PATH

> Base path turned from `/api/v0` to `/api/v1`

---

#### PATH

`/networks/{networkId}/devices/{serial}`

> Deleted

---

#### PATH

`/networks/{networkId}/devices/{serial}/blinkLeds`

> Deleted

---

#### PATH

`/networks/{networkId}/devices/{serial}/lldp_cdp`

> Deleted

---

#### PATH

`/networks/{networkId}/devices/{serial}/lossAndLatencyHistory`

> Deleted

---

#### PATH

`/networks/{networkId}/devices/{serial}/performance`

> Deleted

---

#### PATH

`/networks/{networkId}/devices/{serial}/reboot`

> Deleted

---

#### PATH

`/networks/{networkId}/devices/{serial}/remove`

> Deleted

---

#### PATH

`/networks/{networkId}/devices/{serial}/uplink`

> Deleted

---

### SSIDs

**Update the attributes of an SSID**

#### PUT

`/networks/{networkId}/ssids/{number}`

> Property `walledGardenRanges` type turn from `string` to `array`

---

### Networks

**Create a network**

#### POST

`/organizations/{organizationId}/networks`

> **Required property** `productTypes` Added

---
