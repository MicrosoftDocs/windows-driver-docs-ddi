---
UID: NF:netadapteroffload.NetOffloadIsUsoIPv6Enabled
title: NetOffloadIsUsoIPv6Enabled function (netadapteroffload.h)
author: windows-driver-content
description: The NetOffloadIsUsoIPv6Enabled method determines whether a net adapter has UDP send offload (USO) enabled for IPv6 packets.
tech.root: netvista
ms.assetid: c56d63ef-d111-44e3-a2e7-226bc45dc357
ms.author: windowsdriverdev
ms.date: 01/17/2019
keywords: ["NetOffloadIsUsoIPv6Enabled function"]
f1_keywords:
 - "netadapteroffload/NetOffloadIsUsoIPv6Enabled"
ms.keywords: NetOffloadIsUsoIPv6Enabled
req.header: netadapteroffload.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.29
req.umdf-ver:
req.lib: netadaptercxstub.lib
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- LibDef
api_location: 
- netadaptercxstub.lib
api_name: 
- NetOffloadIsUsoIPv6Enabled
product:
- Windows
targetos: Windows
---

# NetOffloadIsUsoIPv6Enabled function


## -description

The **NetOffloadIsUsoIPv6Enabled** method determines whether a net adapter has UDP send offload (USO) enabled for IPv6 packets.

## -parameters

### -param Offload

A NETOFFLOAD object that represents the net adapter's generic send offload (GSO) capabilities.

## -returns

Returns **TRUE** if USO is enabled for IPv6 packets, or **FALSE** if it is not.

## -remarks

Client drivers typically call this method during their [*EvtNetAdapterOffloadSetGso*](../netadapteroffload/nc-netadapteroffload-evt_net_adapter_offload_set_gso.md) callback to test whether an updated set of active GSO capabilities includes USO for IPv6 packets.

## -see-also

[NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[*EVT_NET_ADAPTER_OFFLOAD_SET_GSO*](../netadapteroffload/nc-netadapteroffload-evt_net_adapter_offload_set_gso.md)
