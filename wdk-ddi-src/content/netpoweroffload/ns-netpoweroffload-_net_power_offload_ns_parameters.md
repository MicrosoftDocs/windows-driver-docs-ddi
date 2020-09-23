---
UID: NS:netpoweroffload._NET_POWER_OFFLOAD_NS_PARAMETERS
title: NET_POWER_OFFLOAD_NS_PARAMETERS (netpoweroffload.h)
author: windows-driver-content
description: The NET_POWER_OFFLOAD_NS_PARAMETERS structure contains IPv6 NS low-power protocol offload parameters for a net adapter.
tech.root: netvista
ms.assetid: 4ebf3a7f-90b5-43dd-8c28-33319fdf0d59
ms.author: windowsdriverdev
ms.date: 09/30/2019
keywords: ["NET_POWER_OFFLOAD_NS_PARAMETERS structure"]
ms.keywords: NET_POWER_OFFLOAD_NS_PARAMETERS, NET_POWER_OFFLOAD_NS_PARAMETERS,
req.header: netpoweroffload.h
req.include-header: netadaptercx.h 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: NET_POWER_OFFLOAD_NS_PARAMETERS
targetos: Windows
ms.custom: Vb
f1_keywords:
 - _NET_POWER_OFFLOAD_NS_PARAMETERS
 - netpoweroffload/_NET_POWER_OFFLOAD_NS_PARAMETERS
 - NET_POWER_OFFLOAD_NS_PARAMETERS
 - netpoweroffload/NET_POWER_OFFLOAD_NS_PARAMETERS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netpoweroffload.h
api_name:
 - NET_POWER_OFFLOAD_NS_PARAMETERS
product:
 - Windows
---

# NET_POWER_OFFLOAD_NS_PARAMETERS structure


## -description

The **NET_POWER_OFFLOAD_NS_PARAMETERS** structure contains parameters for an IPv6 Neighbor Solitication (NS) low power protocol offload to a net adapter.

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field Id

The identifier for this protocol offload.

### -field RemoteIPv6Address

The Source Address Field in the IPv6 header of the NS message. This member is optional.

If the incoming NS message has a Source Address value that matches this IPv6 address, the net adapter sends a neighbor advertisement (NA) message when it is in a low power state. If this member is zero, the net adapter should respond to NS messages from any remote IPv6 address.

### -field SolicitedNodeIPv6Address

The solicited node IPv6 address.

### -field TargetIPv6Addresses

An array that contains one or two IPv6 addresses. If it contains only one address, that address is stored in the first element in the array and the second element is filled with zeros. 

Client drivers must consume all addresses in the array.

These addresses represent the Target Address field of an NS message. If one of these addresses matches the Target Address field of an incoming NS message, the net adapter sends an NA message in response.

### -field LinkLayerAddress

 
The media access control (MAC) address. When it sends the NA message, the net adapter uses this address for the target link layer address (TLLA) field of the NA message.

> [!NOTE]
> When it sends an NA message, the net adapter must always use this MAC address in the TLLA field of the NA message. However, it should use the current MAC address of the net adapter as the source address in the MAC header.

## -remarks

Call [**NET_POWER_OFFLOAD_NS_PARAMETERS_INIT**](../netpoweroffload/nf-netpoweroffload-net_power_offload_ns_parameters_init.md) to initialize this structure and fill in its **Size** field. After calling **NET_POWER_OFFLOAD_NS_PARAMETERS_INIT**, call [**NetPowerOffloadGetNsParameters**](../netpoweroffload/nf-netpoweroffload-netpoweroffloadgetnsparameters.md) to fill in the remaining members of the structure.

For more information about IPv6 NS and NA messages, see [RFC 4861](https://www.ietf.org/rfc/rfc4861.txt).

## -see-also

[Configuring power management](/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_POWER_OFFLOAD_NS_PARAMETERS_INIT**](../netpoweroffload/nf-netpoweroffload-net_power_offload_ns_parameters_init.md)

[**NetPowerOffloadGetNsParameters**](../netpoweroffload/nf-netpoweroffload-netpoweroffloadgetnsparameters.md)