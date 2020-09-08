---
UID: NF:netadapteroffload.NetOffloadIsRscTimestampEnabled
title: NetOffloadIsRscTimestampEnabled function (netadapteroffload.h)
author: windows-driver-content
description: The NetOffloadIsRscTimestampEnabled function determines whether a net adapter has RSC offload enabled for timestamp packets.
tech.root: netvista
ms.assetid: d602c7b6-eab2-4929-a124-c2f46a98947a
ms.author: windowsdriverdev
ms.date: 11/07/2019
keywords: ["NetOffloadIsRscTimestampEnabled function"]
ms.keywords: NetOffloadIsRscTimestampEnabled
req.header: netadapteroffload.h
req.include-header: netadaptercx.h 
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
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
ms.custom: Vb
f1_keywords:
 - NetOffloadIsRscTimestampEnabled
 - netadapteroffload/NetOffloadIsRscTimestampEnabled
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - netadaptercxstub.lib
api_name:
 - NetOffloadIsRscTimestampEnabled
product:
 - Windows
---

# NetOffloadIsRscTimestampEnabled function


## -description

The **NetOffloadIsRscTimestampEnabled** function determines whether a net adapter has RSC offload enabled for timestamp packets.

## -parameters

### -param Offload

A NETOFFLOAD object that represents the net adapter's RSC capabilities.

## -returns

Returns **TRUE** if RSC offload is enabled for timestamp packets, or **FALSE** if it is not.

## -remarks

Client drivers typically call this function during their [*EvtNetAdapterOffloadSetRsc*](../netadapteroffload/nc-netadapteroffload-evt_net_adapter_offload_set_rsc.md) callback to test whether an updated set of active RSC capabilities includes RSC offload for timestamp packets.

## -see-also

[NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[*EVT_NET_ADAPTER_OFFLOAD_SET_RSC*](../netadapteroffload/nc-netadapteroffload-evt_net_adapter_offload_set_rsc.md)

