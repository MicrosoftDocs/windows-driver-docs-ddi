---
UID: NF:netadapteroffload.NetOffloadIsRxChecksumUdpEnabled
title: NetOffloadIsRxChecksumUdpEnabled function (netadapteroffload.h)
author: windows-driver-content
description: The NetOffloadIsRxChecksumUdpEnabled method determines whether a net adapter has Rx UDP checksum offload enabled.
tech.root: netvista
ms.assetid: c56d63ef-d111-44e3-a2e7-226bc45dc357
ms.author: windowsdriverdev
ms.date: 01/17/2019
keywords: ["NetOffloadIsRxChecksumUdpEnabled function"]
f1_keywords:
 - "netadapteroffload/NetOffloadIsRxChecksumUdpEnabled"
ms.keywords: NetOffloadIsRxChecksumUdpEnabled
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
- NetOffloadIsRxChecksumUdpEnabled
product:
- Windows
targetos: Windows
---

# NetOffloadIsRxChecksumUdpEnabled function


## -description

The **NetOffloadIsRxChecksumUdpEnabled** method determines whether a net adapter has Rx UDP checksum offload enabled.

## -parameters

### -param Offload

A NETOFFLOAD object that represents the net adapter's Rx checksum capabilities.

## -returns

Returns **TRUE** if Rx UDP checksum offload is enabled, or **FALSE** if it is not.

## -remarks

Client drivers typically call this method during their [*EvtNetAdapterOffloadSetRxChecksum*](../netadapteroffload/nc-netadapteroffload-evt_net_adapter_offload_set_rx_checksum.md) callback to test whether an updated set of active Rx checksum capabilities includes Rx UDP checksum offload.

## -see-also

[NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[*EVT_NET_ADAPTER_OFFLOAD_SET_RX_CHECKSUM*](../netadapteroffload/nc-netadapteroffload-evt_net_adapter_offload_set_rx_checksum.md)
