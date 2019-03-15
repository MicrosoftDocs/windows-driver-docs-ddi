---
UID: NS:wwan.__unnamed_union_0
title: WWAN_IP_CONFIGURATION_FLAGS (wwan.h)
description: The WWAN_IP_CONFIGURATION_FLAGS structure represents flags that describe the availability of the IP address, gateway, DNS server, and/or MTU information of a PDP context.
old-location: netvista\wwan_ip_configuration_flags.htm
tech.root: netvista
ms.assetid: 5157F48F-E1D3-4B22-BBB0-0FC7965C794B
ms.date: 05/02/2018
ms.keywords: WWAN_IP_CONFIGURATION_FLAGS, WWAN_IP_CONFIGURATION_FLAGS union [Network Drivers Starting with Windows Vista], netvista.wwan_ip_configuration_flags, wwan/WWAN_IP_CONFIGURATION_FLAGS
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wwan.h
api_name:
- WWAN_IP_CONFIGURATION_FLAGS
product:
- Windows
targetos: Windows
req.typenames: WWAN_IP_CONFIGURATION_FLAGS
---

# WWAN_IP_CONFIGURATION_FLAGS structure


## -description


The WWAN_IP_CONFIGURATION_FLAGS structure represents flags that describe the availability of the IP address, gateway, DNS server, and/or MTU information of a PDP context.


## -struct-fields




### -field Value

Reserved. Do not use.


### -field AddressAvailable

An address is available.

### -field GatewayAvailable

A gateway is available.

### -field DnsServerAvailable

A DNS server is available.

### -field MTUAvailable

An MTU is available.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn449758">WWAN_IP_CONFIGURATION_FLAGS</a>
 

 

