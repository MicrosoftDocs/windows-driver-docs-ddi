---
UID: NC:netadapteroffload.EVT_NET_ADAPTER_OFFLOAD_SET_RSC
title: EVT_NET_ADAPTER_OFFLOAD_SET_RSC (netadapteroffload.h)
author: windows-driver-content
description: The EvtNetAdapterOffloadSetRsc callback function is implemented by the client driver to set changes in active receive segment coalescence (RSC) offload capabilities.
tech.root: netvista
ms.assetid: b23d877b-4f75-497b-8b2c-5082eaba2ba2
ms.author: windowsdriverdev
ms.date: 11/07/2019
ms.topic: callback
f1_keywords:
 - "netadapteroffload/EVT_NET_ADAPTER_OFFLOAD_SET_RSC"
req.header: netadapteroffload.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: The next version of Windows 10
req.target-min-winversvr:
req.kmdf-ver:
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
 - UserDefined
api_location: 
 - netadapteroffload.h
api_name: 
 - EVT_NET_ADAPTER_OFFLOAD_SET_RSC
product: 
 - Windows
targetos: Windows
ms.custom: Vb
---

# EVT_NET_ADAPTER_OFFLOAD_SET_RSC callback function

## -description

The *EvtNetAdapterOffloadSetRsc* callback function is implemented by the client driver to set changes in active receive segment coalescence (RSC) offload capabilities.

## -prototype

```C++
//Declaration

EVT_NET_ADAPTER_OFFLOAD_SET_LSO EvtNetAdapterOffloadSetRsc; 

// Definition

VOID EvtNetAdapterOffloadSetRsc 
(
	NETADAPTER Adapter,
	NETOFFLOAD Offload
)
{...}

```

## -parameters

### -param Adapter

A handle to a NETADAPTER object the client driver previously created with a call to [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md).

### -param Offload 

A handle to a NETOFFLOAD object that describes the adapter's offload capabilities.

## -returns

This callback function does not return a value.

## -remarks

Register your implementation of this callback function by setting the appropriate parameter when calling [**NetAdapterOffloadSetRscCapabilities**](nf-netadapteroffload-netadapteroffloadsetrsccapabilities.md).

For more info, see [NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads).

## -see-also

[NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[**NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES**](ns-netadapteroffload-_net_adapter_offload_rsc_capabilities.md)

[**NetAdapterOffloadSetRscCapabilities**](nf-netadapteroffload-netadapteroffloadsetrsccapabilities.md)