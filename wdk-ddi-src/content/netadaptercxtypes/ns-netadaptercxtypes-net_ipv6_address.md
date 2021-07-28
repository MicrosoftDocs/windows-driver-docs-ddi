---
UID: NS:netadaptercxtypes._NET_IPV6_ADDRESS
title: NET_IPV6_ADDRESS (netadaptercxtypes.h)
description: The NET_IPV6_ADDRESS union specifies an IPv6 address.
tech.root: netvista
ms.date: 04/15/2021
keywords: ["NET_IPV6_ADDRESS structure"]
ms.keywords: NET_IPV6_ADDRESS, NET_IPV6_ADDRESS,
req.header: netadaptercxtypes.h
req.include-header: netadaptercx.h
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: NET_IPV6_ADDRESS
targetos: Windows
ms.custom: Vb
f1_keywords:
 - _NET_IPV6_ADDRESS
 - netadaptercxtypes/_NET_IPV6_ADDRESS
 - NET_IPV6_ADDRESS
 - netadaptercxtypes/NET_IPV6_ADDRESS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadaptercxtypes.h
api_name:
 - _NET_IPV6_ADDRESS
 - NET_IPV6_ADDRESS
product:
 - Windows
---

# NET_IPV6_ADDRESS union


## -description

The **NET_IPV6_ADDRESS** union specifies an IPv6 address.

## -struct-fields

### -field Unicast

A structure that represents a IPv6 unicast address and contains the **NetworkPrefix** and **InterfaceIdentifier** values.

### -field Unicast.NetworkPrefix

A UINT64 value that represents the network prefix.

### -field Unicast.InterfaceIdentifier

A UINT64 value that represents the interface identifier.

### -field Value

A UINT8 array that represents an IPv6 address.

## -remarks

## -see-also

[**NET_IPV4_ADDRESS**](ns-netadaptercxtypes-net_ipv4_address.md)

