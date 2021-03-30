Version **1.6.0** _to_ **1.7.0**

What's Updated
==============

\[ networks \]
--------------

GET _`/networks/{networkId}`_

> \- Response property `notes` value added

* * *

GET _`/networks/{networkId}/settings`_

> \- Response property `secureConnect` value added

* * *

PUT _`/networks/{networkId}/settings`_

> \- Optional property `secureConnect` Added

* * *

\[ organizations \]
-------------------

GET _`/organizations/{organizationId}/networks`_

> \- Response property `notes` value added

* * *

\[ switch \]
------------

PATH _`/networks/{networkId}/switch/alternateManagementInterface`_

> \- Path added  
>   
> \- New endpoint
> 
> #### Return the switch alternate management interface for the network
> 
> **GET** `/networks/{networkId}/switch/alternateManagementInterface`  
> 
>     {
>         "enabled": true,
>         "vlanId": 100,
>         "protocols": [
>             "radius",
>             "snmp",
>             "syslog"
>         ],
>         "switches": [
>             {
>                 "serial": "Q234-ABCD-5678",
>                 "alternateManagementIp": "1.2.3.4"
>             }
>         ]
>     }
> 
> * * *
> 
>   
> \- New endpoint
> 
> #### Update the switch alternate management interface for the network
> 
> **PUT** `/networks/{networkId}/switch/alternateManagementInterface`  
> 
>     {
>         "enabled": true,
>         "vlanId": 100,
>         "protocols": [
>             "radius",
>             "snmp",
>             "syslog"
>         ],
>         "switches": [
>             {
>                 "serial": "Q234-ABCD-5678",
>                 "alternateManagementIp": "1.2.3.4"
>             }
>         ]
>     }
> 
> * * *

* * *

What's Changed
==============

\[ global \]
------------

PATH _`/networks/{networkID}/clients/applicationUsage`_

> \- renamed to `/networks/{networkId}/clients/applicationUsage`

* * *

PATH _`/networks/{networkID}/clients/usageHistories`_

> \- renamed to `/networks/{networkId}/clients/usageHistories`

* * *