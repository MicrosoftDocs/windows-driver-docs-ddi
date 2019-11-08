---
UID: NF:netadapteroffload.NetOffloadIsRscIPv4Enabled
title: NetOffloadIsRscIPv4Enabled function (netadapteroffload.h)
author: windows-driver-content
description: The NetOffloadIsRscIPv4Enabled method determines whether a net adapter has RSC offload enabled for IPv4 packets.
tech.root: netvista
ms.assetid: 431cdc87-473f-40f1-9ade-14e3e7459cbd
ms.author: windowsdriverdev
ms.date: 11/07/2019
ms.topic: function
f1_keywords:
 - "netadapteroffload/NetOffloadIsRscIPv4Enabled"
ms.keywords: NetOffloadIsRscIPv4Enabled
req.header: netadapteroffload.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: The next version of Windows 10
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
topic_type: 
- apiref
api_type: 
- LibDef
api_location: 
- netadaptercxstub.lib
api_name: 
- NetOffloadIsRscIPv4Enabled
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NetOffloadIsRscIPv4Enabled function


## -description

The **NetOffloadIsRscIPv4Enabled** method determines whether a net adapter has RSC offload enabled for IPv4 packets.

## -parameters

### -param Offload

A NETOFFLOAD object that represents the net adapter's RSC capabilities.

## -returns

Returns **TRUE** if RSC offload is enabled for IPv4 packets, or **FALSE** if it is not.

## -remarks

Client drivers typically call this method during their [*EvtNetAdapterOffloadSetRsc*](../netadapteroffload/nc-netadapteroffload-evt_net_adapter_offload_set_rsc.md) callback to test whether an updated set of active RSC capabilities includes RSC offload for IPv4 packets.

## -see-also

[NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[*EVT_NET_ADAPTER_OFFLOAD_SET_RSC*](../netadapteroffload/nc-netadapteroffload-evt_net_adapter_offload_set_rsc.md)