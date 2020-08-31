---
UID: NF:netreceivescaling.NetAdapterSetReceiveScalingCapabilities
title: NetAdapterSetReceiveScalingCapabilities function (netreceivescaling.h)
description: The NetAdapterSetReceiveScalingCapabilities function sets a net adapter's receive side scaling (RSS) capabilities.
tech.root: netvista
ms.assetid: facda650-4f68-40e4-bfe0-f9b7adae4c7f
ms.date: 03/08/2018
keywords: ["NetAdapterSetReceiveScalingCapabilities function"]
f1_keywords:
 - "netreceivescaling/NetAdapterSetReceiveScalingCapabilities"
 - "NetAdapterSetReceiveScalingCapabilities"
ms.keywords: NetAdapterSetReceiveScalingCapabilities
req.header: netreceivescaling.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.lib:
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
- DllExport
api_location:
- NtosKrnl.exe
api_name: 
- NetAdapterSetReceiveScalingCapabilities
targetos: Windows

---

# NetAdapterSetReceiveScalingCapabilities function


## -description


The **NetAdapterSetReceiveScalingCapabilities** function sets a net adapter's receive side scaling (RSS) capabilities.

## -parameters

### -param Adapter
The **NETADAPTER** object the driver obtained in a previous call to [NetAdapterCreate](../netadapter/nf-netadapter-netadaptercreate.md).

### -param Capabilities
A pointer to a driver-allocated and initialized [NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES](ns-netreceivescaling-_net_adapter_receive_scaling_capabilities.md) structure.

## -remarks

The client driver must call this function when starting a net adapter, before calling [**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md).

## -see-also
[NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES](ns-netreceivescaling-_net_adapter_receive_scaling_capabilities.md)

[NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES_INIT](nf-netreceivescaling-net_adapter_receive_scaling_capabilities_init.md)

[NetAdapterCx Receive Side Scaling](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling-rss-)
