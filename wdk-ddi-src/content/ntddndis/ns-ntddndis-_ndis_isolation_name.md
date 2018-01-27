---
UID: NS:ntddndis._NDIS_ISOLATION_NAME
title: _NDIS_ISOLATION_NAME
author: windows-driver-content
description: The NDIS_ISOLATION_NAME structure contains an NDIS isolation name for a VM network adapter.
old-location: netvista\ndis_isolation_name.htm
old-project: netvista
ms.assetid: 4712F853-8819-476C-8AD9-426EA5A0802E
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NDIS_ISOLATION_NAME, netvista.ndis_isolation_name, _NDIS_ISOLATION_NAME, *PNDIS_ISOLATION_ID_NAME, NDIS_ISOLATION_ID_NAME, NDIS_ISOLATION_NAME structure [Network Drivers Starting with Windows Vista], ntddndis/NDIS_ISOLATION_NAME, *PNDIS_ROUTING_DOMAIN_NAME, NDIS_ROUTING_DOMAIN_NAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Ntddndis.h
apiname: 
-	NDIS_ISOLATION_NAME
product: Windows
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



## -syntax


````
typedef NDIS_ISOLATION_NAME NDIS_ISOLATION_ID_NAME, *PNDIS_ISOLATION_ID_NAME;
typedef NDIS_ISOLATION_NAME NDIS_ROUTING_DOMAIN_NAME, *PNDIS_ROUTING_DOMAIN_NAME;

````


## -struct-fields




### -field Length

Length, in bytes, of the NDIS isolation name. This member must be less than or equal to <b>NDIS_ISOLATION_NAME_MAX_STRING_SIZE</b>.


### -field String

A <b>NULL</b>-terminated string that contains the NDIS isolation name. The isolation name can be an isolation ID name or a routing domain name.


## -remarks


This structure is used in:<ul>
<li>
The <b>IsolationIdName</b> member of the <a href="..\ntddndis\ns-ntddndis-_ndis_routing_domain_isolation_entry.md">NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY</a> structure.

</li>
<li>
The <b>RoutingDomainName</b> member of the <a href="..\ntddndis\ns-ntddndis-_ndis_routing_domain_entry.md">NDIS_ROUTING_DOMAIN_ENTRY</a> structure.

</li>
<li>
The <b>RoutingDomainName</b> member of the <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_routing_domain.md">NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN</a> structure.

</li>
</ul>




## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_routing_domain.md">NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_routing_domain_entry.md">NDIS_ROUTING_DOMAIN_ENTRY</a>

<a href="..\ntddndis\ne-ntddndis-_ndis_isolation_mode.md">NDIS_ISOLATION_MODE</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_routing_domain_isolation_entry.md">NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_ISOLATION_NAME structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

