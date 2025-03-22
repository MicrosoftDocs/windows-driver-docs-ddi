---
UID: NF:netadapteroffload.NetOffloadIsUdpRscEnabled
tech.root: netvista
title: NetOffloadIsUdpRscEnabled
ms.date: 05/10/2024
targetos: Windows
description: The NetOffloadIsUdpRscEnabled function determines whether a net adapter has UDP RSC Offload (URO) enabled.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: netadapteroffload.h
req.idl: 
req.include-header: netadaptercx.h
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 1.33
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 2.33
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapteroffload.h
api_name:
 - NetOffloadIsUdpRscEnabled
f1_keywords:
 - NetOffloadIsUdpRscEnabled
 - netadapteroffload/NetOffloadIsUdpRscEnabled
dev_langs:
 - c++
helpviewer_keywords:
 - NetOffloadIsUdpRscEnabled
---

# NetOffloadIsUdpRscEnabled function (netadapteroffload.h)

## -description

The **NetOffloadIsUdpRscEnabled** function determines whether a network adapter has [UDP RSC Offload (URO)](/windows-hardware/drivers/netcx/rsc-offload#udp-rsc-offload-uro-) enabled.

## -parameters

### -param Offload [_In_]

A NETOFFLOAD object that represents the network adapter's URO capabilities.

## -returns

Returns **TRUE** if URO is enabled. Otherwise, returns **FALSE**.

## -remarks

Client drivers typically call this function during their [*EvtNetAdapterOffloadSetRsc*](../netadapteroffload/nc-netadapteroffload-evt_net_adapter_offload_set_rsc.md) callback to test whether an updated set of active RSC capabilities includes URO.

## -see-also

[UDP RSC Offload (URO)](/windows-hardware/drivers/netcx/rsc-offload#udp-rsc-offload-uro-)

[*EvtNetAdapterOffloadSetRsc*](../netadapteroffload/nc-netadapteroffload-evt_net_adapter_offload_set_rsc.md)

