---
UID: NS:wwan.WWAN_IP_CONFIGURATION_FLAGS
title: WWAN_IP_CONFIGURATION_FLAGS
author: windows-driver-content
description: The WWAN_IP_CONFIGURATION_FLAGS structure represents flags that describe the availability of the IP address, gateway, DNS server, and/or MTU information of a PDP context.
old-location: netvista\wwan_ip_configuration_flags.htm
old-project: netvista
ms.assetid: 5157F48F-E1D3-4B22-BBB0-0FC7965C794B
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.wwan_ip_configuration_flags, WWAN_IP_CONFIGURATION_FLAGS, wwan/WWAN_IP_CONFIGURATION_FLAGS, WWAN_IP_CONFIGURATION_FLAGS union [Network Drivers Starting with Windows Vista]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wwan.h
apiname:
-	WWAN_IP_CONFIGURATION_FLAGS
product: Windows
targetos: Windows
req.typenames: WWAN_IP_CONFIGURATION_FLAGS
req.product: Windows 10 or later.
---

# WWAN_IP_CONFIGURATION_FLAGS structure


## -description


The WWAN_IP_CONFIGURATION_FLAGS structure represents flags that describe the availability of the IP address, gateway, DNS server, and/or MTU information of a PDP context.


## -syntax


````
typedef union {
  ULONG  Value;
  struct {
    ULONG AddressAvailable:1;
    ULONG GatewayAvailable:1;
    ULONG DnsServerAvailable:1;
    ULONG MTUAvailable:1;
  };
} WWAN_IP_CONFIGURATION_FLAGS;
````


## -struct-fields




### -field Value

Reserved. Do not use.


### -field AddressAvailable

 


### -field GatewayAvailable

 


### -field DnsServerAvailable

 


### -field MTUAvailable

 




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

<a href="..\wwan\ns-wwan-wwan_ip_configuration_flags.md">WWAN_IP_CONFIGURATION_FLAGS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_IP_CONFIGURATION_FLAGS union%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

