---
UID: NF:netadapteroffload.NetOffloadIsLsoIPv4Enabled
title: NetOffloadIsLsoIPv4Enabled function (netadapteroffload.h)
author: windows-driver-content
description: The NetOffloadIsLsoIPv4Enabled function determines whether a net adapter has LSO offload enabled for IPv4 packets.
tech.root: netvista
ms.assetid: c56d63ef-d111-44e3-a2e7-226bc45dc357
ms.author: windowsdriverdev
ms.date: 01/17/2019
keywords: ["NetOffloadIsLsoIPv4Enabled function"]
ms.keywords: NetOffloadIsLsoIPv4Enabled
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
targetos: Windows
f1_keywords:
 - NetOffloadIsLsoIPv4Enabled
 - netadapteroffload/NetOffloadIsLsoIPv4Enabled
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - netadaptercxstub.lib
api_name:
 - NetOffloadIsLsoIPv4Enabled
---

# NetOffloadIsLsoIPv4Enabled function


## -description

The **NetOffloadIsLsoIPv4Enabled** function determines whether a net adapter has LSO offload enabled for IPv4 packets.

## -parameters

### -param Offload

A NETOFFLOAD object that represents the net adapter's LSO capabilities.

## -returns

Returns **TRUE** if LSO offload is enabled for IPv4 packets, or **FALSE** if it is not.

## -remarks

Client drivers typically call this function during their [*EvtNetAdapterOffloadSetLso*](../netadapteroffload/nc-netadapteroffload-evt_net_adapter_offload_set_lso.md) callback to test whether an updated set of active LSO capabilities includes LSO offload for IPv4 packets.

## -see-also

[NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[*EVT_NET_ADAPTER_OFFLOAD_SET_LSO*](../netadapteroffload/nc-netadapteroffload-evt_net_adapter_offload_set_lso.md)

