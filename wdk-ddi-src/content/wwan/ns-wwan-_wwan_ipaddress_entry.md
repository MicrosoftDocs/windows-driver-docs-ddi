---
UID: NS:wwan._WWAN_IPADDRESS_ENTRY
title: _WWAN_IPADDRESS_ENTRY (wwan.h)
description: The WWAN_IPADDRESS_ENTRY structure represents either the IPV4 or IPV6 address of a PDP context.
old-location: netvista\wwan_ipaddress_entry.htm
tech.root: netvista
ms.assetid: 85615799-5AA0-4D83-9246-73F3C7ABFFF6
ms.date: 05/02/2018
ms.keywords: "*PWWAN_IPADDRESS_ENTRY, PWWAN_IPADDRESS_ENTRY, PWWAN_IPADDRESS_ENTRY structure pointer [Network Drivers Starting with Windows Vista], WWAN_IPADDRESS_ENTRY, WWAN_IPADDRESS_ENTRY structure [Network Drivers Starting with Windows Vista], _WWAN_IPADDRESS_ENTRY, netvista.wwan_ipaddress_entry, wwan/PWWAN_IPADDRESS_ENTRY, wwan/WWAN_IPADDRESS_ENTRY"
ms.topic: struct
f1_keywords:
 - "wwan/WWAN_IPADDRESS_ENTRY"
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
- WWAN_IPADDRESS_ENTRY
product:
- Windows
targetos: Windows
req.typenames: WWAN_IPADDRESS_ENTRY, *PWWAN_IPADDRESS_ENTRY
---

# _WWAN_IPADDRESS_ENTRY structure


## -description


The WWAN_IPADDRESS_ENTRY structure represents either the IPV4 or IPV6 address of a PDP context.


## -struct-fields




### -field IsIpv6

Set if the IP address of the PDP context is an IPV6 address.

### -field IsReported

Reserved. Do not use.

### -field Ipv4

The IPV4 address of the PDP context, if <b>IsIpv6</b> is not set.

### -field Ipv6

The IPV6 address of the PDP context, if <b>IsIpv6</b> is set.
