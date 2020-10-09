---
UID: NF:netadapteroffload.NetOffloadIsLsoIPv4Enabled
title: NetOffloadIsLsoIPv4Enabled function (netadapteroffload.h)
author: windows-driver-content
description: The NetOffloadIsLsoIPv4Enabled function determines whether a net adapter has large send offload (LSO) enabled for IPv4 packets.
tech.root: netvista
ms.assetid: c56d63ef-d111-44e3-a2e7-226bc45dc357
ms.author: windowsdriverdev
ms.date: 10/09/2020
keywords: ["NetOffloadIsLsoIPv4Enabled function"]
f1_keywords:
 - "netadapteroffload/NetOffloadIsLsoIPv4Enabled"
ms.keywords: NetOffloadIsLsoIPv4Enabled
req.header: netadapteroffload.h
req.include-header: netadaptercx.h
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
- NetOffloadIsLsoIPv4Enabled
product:
- Windows
targetos: Windows
---

# NetOffloadIsLsoIPv4Enabled function


## -description

The **NetOffloadIsLsoIPv4Enabled** function determines whether a net adapter has large send offload (LSO) enabled for IPv4 packets.

## -parameters

### -param Offload

[_In_] A NETOFFLOAD object that represents the net adapter's generic send offload (GSO) capabilities.

## -returns

Returns **TRUE** if LSO is enabled for IPv4 packets, or **FALSE** if it is not.

## -remarks

Client drivers typically call this function during their [*EVT_NET_ADAPTER_OFFLOAD_SET_GSO*](../netadapteroffload/nc-netadapteroffload-evt_net_adapter_offload_set_gso.md) callback to test whether an updated set of active GSO capabilities includes LSO for IPv4 packets.

## -see-also

[Generic Segmentation Offload](/windows-hardware/drivers/netcx/gso-offload)

[*EVT_NET_ADAPTER_OFFLOAD_SET_GSO*](nc-netadapteroffload-evt_net_adapter_offload_set_gso.md)
