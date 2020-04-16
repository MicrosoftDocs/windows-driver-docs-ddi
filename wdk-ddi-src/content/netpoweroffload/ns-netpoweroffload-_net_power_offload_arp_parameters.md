---
UID: NS:netpoweroffload._NET_POWER_OFFLOAD_ARP_PARAMETERS
title: NET_POWER_OFFLOAD_ARP_PARAMETERS (netpoweroffload.h)
author: windows-driver-content
description: The NET_POWER_OFFLOAD_ARP_PARAMETERS structure contains IPv4 ARP low-power protocol offload parameters for a net adapter.
tech.root: netvista
ms.assetid: bec3ab2b-5884-4c7d-895a-76b8a44126bf
ms.author: windowsdriverdev
ms.date: 09/30/2019
keywords: ["NET_POWER_OFFLOAD_ARP_PARAMETERS structure"]
f1_keywords:
 - "netpoweroffload/NET_POWER_OFFLOAD_ARP_PARAMETERS"
ms.keywords: NET_POWER_OFFLOAD_ARP_PARAMETERS, NET_POWER_OFFLOAD_ARP_PARAMETERS, 
req.header: netpoweroffload.h
req.include-header:
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
req.typenames: NET_POWER_OFFLOAD_ARP_PARAMETERS
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - netpoweroffload.h
api_name: 
 - NET_POWER_OFFLOAD_ARP_PARAMETERS
product: 
 - Windows
targetos: Windows
ms.custom: Vb
---

# NET_POWER_OFFLOAD_ARP_PARAMETERS structure

## -description

The **NET_POWER_OFFLOAD_ARP_PARAMETERS** structure contains parameters for an IPv4 ARP low-power protocol offload to a net adapter.

## -struct-fields

### -field Size

The size of this structure, in bytes.
 
### -field Id

The identifier for this protocol offload.
 
### -field RemoteIPv4Address

The Source Protocol Address (SPA) field of the ARP request. This member is optional.

If the incoming ARP request has an SPA value that matches this IPv4 address, the net adapter sends an ARP response when it is in a low power state. If this member is zero, the net adapter should respond to ARP requests from any remote IPv4 address.
 
### -field HostIPv4Address

The host's IPv4 address. When it sends the ARP response, the net adapter uses this member for the SPA field of the response.
 
### -field LinkLayerAddress

The media access control (MAC) address. The net adapter uses this MAC address for the Source Hardware Address (SHA) field of the ARP response packet that it generates. 

> [!NOTE]
> When it sends an ARP response, the net adapter must always use this MAC address in the ARP payload. However, it should use the current MAC address of the net adapter as the source address in the MAC header.

## -remarks

Call [**NET_POWER_OFFLOAD_ARP_PARAMETERS_INIT**](../netpoweroffload/nf-netpoweroffload-net_power_offload_arp_parameters_init.md) to initialize this structure and fill in its **Size** field. After calling **NET_POWER_OFFLOAD_ARP_PARAMETERS_INIT**, call [**NetPowerOffloadGetArpParameters**](../netpoweroffload/nf-netpoweroffload-netpoweroffloadgetarpparameters.md) to fill in the remaining members of the structure.

For more information about the ARP protocol, see [RFC 826](https://tools.ietf.org/html/rfc826).

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_POWER_OFFLOAD_ARP_PARAMETERS_INIT**](../netpoweroffload/nf-netpoweroffload-net_power_offload_arp_parameters_init.md)

[**NetPowerOffloadGetArpParameters**](../netpoweroffload/nf-netpoweroffload-netpoweroffloadgetarpparameters.md)
