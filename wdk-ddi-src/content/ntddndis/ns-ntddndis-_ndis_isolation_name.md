---
UID: NS:ntddndis._NDIS_ISOLATION_NAME
title: _NDIS_ISOLATION_NAME (ntddndis.h)
description: The NDIS_ISOLATION_NAME structure contains an NDIS isolation name for a VM network adapter.
old-location: netvista\ndis_isolation_name.htm
tech.root: netvista
ms.assetid: 4712F853-8819-476C-8AD9-426EA5A0802E
ms.date: 05/02/2018
keywords: ["_NDIS_ISOLATION_NAME structure"]
ms.keywords: "*PNDIS_ISOLATION_ID_NAME, *PNDIS_ROUTING_DOMAIN_NAME, NDIS_ISOLATION_ID_NAME, NDIS_ISOLATION_NAME, NDIS_ISOLATION_NAME structure [Network Drivers Starting with Windows Vista], NDIS_ROUTING_DOMAIN_NAME, _NDIS_ISOLATION_NAME, netvista.ndis_isolation_name, ntddndis/NDIS_ISOLATION_NAME"
f1_keywords:
 - "ntddndis/NDIS_ISOLATION_NAME"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.40 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddndis.h
api_name:
- NDIS_ISOLATION_NAME
product:
- Windows
targetos: Windows
req.typenames: NDIS_ISOLATION_NAME
---

# _NDIS_ISOLATION_NAME structure


## -description


The <b>NDIS_ISOLATION_NAME</b> structure contains an NDIS isolation name for a VM network adapter. The isolation name can be an isolation ID name or a routing domain name. This structure supports the following derived types:<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef NDIS_ISOLATION_NAME NDIS_ISOLATION_ID_NAME, *PNDIS_ISOLATION_ID_NAME;
typedef NDIS_ISOLATION_NAME NDIS_ROUTING_DOMAIN_NAME, *PNDIS_ROUTING_DOMAIN_NAME;
</pre>
</td>
</tr>
</table></span></div>



## -struct-fields




### -field Length

Length, in bytes, of the NDIS isolation name. This member must be less than or equal to <b>NDIS_ISOLATION_NAME_MAX_STRING_SIZE</b>.


### -field String

A <b>NULL</b>-terminated string that contains the NDIS isolation name. The isolation name can be an isolation ID name or a routing domain name.


## -remarks



This structure is used in:<ul>
<li>
The <b>IsolationIdName</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_routing_domain_isolation_entry">NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY</a> structure.

</li>
<li>
The <b>RoutingDomainName</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_routing_domain_entry">NDIS_ROUTING_DOMAIN_ENTRY</a> structure.

</li>
<li>
The <b>RoutingDomainName</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_routing_domain">NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN</a> structure.

</li>
</ul>





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_isolation_mode">NDIS_ISOLATION_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_routing_domain_entry">NDIS_ROUTING_DOMAIN_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_routing_domain_isolation_entry">NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_routing_domain">NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN</a>
 

 

