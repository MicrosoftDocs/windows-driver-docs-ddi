---
UID: NS:wwan._WWAN_IP_ADDRESS_STATE
title: _WWAN_IP_ADDRESS_STATE
author: windows-driver-content
description: The WWAN_IP_ADDRESS_STATE structure represents the IP addresses, gateways, DNS servers, and/or MTUs of a PDP context.
old-location: netvista\wwan_ip_address_state.htm
old-project: netvista
ms.assetid: 63D3B055-A3B0-4A76-B53C-C5E87C40A52C
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WWAN_IP_ADDRESS_STATE, *PWWAN_IP_ADDRESS_STATE, WWAN_IP_ADDRESS_STATE
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
req.alt-api: WWAN_IP_ADDRESS_STATE
req.alt-loc: wwan.h
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
req.typenames: *PWWAN_IP_ADDRESS_STATE, WWAN_IP_ADDRESS_STATE
req.product: Windows 10 or later.
---

# _WWAN_IP_ADDRESS_STATE structure



## -description
The WWAN_IP_ADDRESS_STATE structure represents the IP addresses, gateways, DNS servers, and/or MTUs of a PDP context.



## -syntax

````
typedef struct _WWAN_IP_ADDRESS_STATE {
  WWAN_IP_CONFIGURATION_FLAGS IPv4Flags;
  WWAN_IP_CONFIGURATION_FLAGS IPv6Flags;
  ULONG                       IPv4MTU;
  ULONG                       IPv6MTU;
  PWWAN_IPADDRESS_ENTRY       IpTable;
  ULONG                       IpCount;
  PWWAN_IPADDRESS_ENTRY       GatewayTable;
  ULONG                       GatewayCount;
  PWWAN_IPADDRESS_ENTRY       DnsTable;
  ULONG                       DnsCount;
} WWAN_IP_ADDRESS_STATE, *PWWAN_IP_ADDRESS_STATE;
````


## -struct-fields

### -field IPv4Flags

Flags that describe  the availability of the IPV4 address, gateway, DNS server, and MTU information of the PDP context.


### -field IPv6Flags

Flags that describe the availability of the IPV6 address, gateway, DNS server, and MTU information of the PDP context.


### -field IPv4MTU

The IPV4 MTU value of the PDP context.


### -field IPv6MTU

The IPV6 MTU value of the PDP context.


### -field IpTable

Pointer to the start of an array of IP addresses of the PDP context.


### -field IpCount

The number of entries in the <b>IpTable</b> array.


### -field GatewayTable

Pointer to the start of an array of gateways of the PDP context.


### -field GatewayCount

The number of entries in the <b>GatewayTable</b> array.


### -field DnsTable

Pointer to the start of an array of DNS servers of the PDP context.


### -field DnsCount

The number of entries in the <b>DnsTable</b> array.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\wwan\ns-wwan-wwan_ip_configuration_flags.md">WWAN_IP_CONFIGURATION_FLAGS</a>
</dt>
<dt>
<a href="..\wwan\ns-wwan-_wwan_ipaddress_entry.md">WWAN_IPADDRESS_ENTRY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_IP_ADDRESS_STATE structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

