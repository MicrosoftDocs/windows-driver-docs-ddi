---
UID: NS:wwan.WWAN_IP_CONFIGURATION_FLAGS
title: WWAN_IP_CONFIGURATION_FLAGS
author: windows-driver-content
description: The WWAN_IP_CONFIGURATION_FLAGS structure represents flags that describe the availability of the IP address, gateway, DNS server, and/or MTU information of a PDP context.
old-location: netvista\wwan_ip_configuration_flags.htm
old-project: netvista
ms.assetid: 5157F48F-E1D3-4B22-BBB0-0FC7965C794B
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: WWAN_IP_CONFIGURATION_FLAGS, WWAN_IP_CONFIGURATION_FLAGS union [Network Drivers Starting with Windows Vista], netvista.wwan_ip_configuration_flags, wwan/WWAN_IP_CONFIGURATION_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8.1 and later versions of Windows.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_IP_CONFIGURATION_FLAGS
product: Windows
targetos: Windows
req.typenames: WWAN_IP_CONFIGURATION_FLAGS
req.product: Windows 10 or later.
---

# WWAN_IP_CONFIGURATION_FLAGS structure


## -description


The WWAN_IP_CONFIGURATION_FLAGS structure represents flags that describe the availability of the IP address, gateway, DNS server, and/or MTU information of a PDP context.


## -struct-fields




### -field Value

Reserved. Do not use.


#### - ( unnamed struct )

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
struct
{
    ULONG    AddressAvailable:1;
    ULONG    GatewayAvailable:1;
    ULONG    DnsServerAvailable:1;
    ULONG    MTUAvailable:1;
};</pre>
</td>
</tr>
</table></span></div>


#### AddressAvailable:1

An address is available.



#### GatewayAvailable:1

A gateway is available.



#### DnsServerAvailable:1

A DNS server is available.



#### MTUAvailable:1

An MTU is available.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn449758">WWAN_IP_CONFIGURATION_FLAGS</a>
 

 

