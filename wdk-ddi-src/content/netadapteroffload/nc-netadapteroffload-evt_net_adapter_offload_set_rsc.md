---
UID: NC:netadapteroffload.EVT_NET_ADAPTER_OFFLOAD_SET_RSC
title: EVT_NET_ADAPTER_OFFLOAD_SET_RSC (netadapteroffload.h)
description: The EvtNetAdapterOffloadSetRsc callback function is implemented by the client driver to set changes in active receive segment coalescence (RSC) offload capabilities.
tech.root: netvista
ms.assetid: b23d877b-4f75-497b-8b2c-5082eaba2ba2
ms.date: 11/07/2019
keywords: ["EVT_NET_ADAPTER_OFFLOAD_SET_RSC callback function"]
req.header: netadapteroffload.h
req.include-header: netadaptercx.h 
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 2004
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
targetos: Windows
ms.custom: Vb
f1_keywords:
 - EVT_NET_ADAPTER_OFFLOAD_SET_RSC
 - netadapteroffload/EVT_NET_ADAPTER_OFFLOAD_SET_RSC
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
---

# EVT_NET_ADAPTER_OFFLOAD_SET_RSC callback function


## -description

The *EvtNetAdapterOffloadSetRsc* callback function is implemented by the client driver to set changes in active receive segment coalescence (RSC) offload capabilities.

## -parameters

### -param Adapter

A handle to a NETADAPTER object the client driver previously created with a call to [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md).

### -param Offload 

A handle to a NETOFFLOAD object that describes the adapter's offload capabilities.

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

## -remarks

Register your implementation of this callback function by setting the appropriate parameter when calling [**NetAdapterOffloadSetRscCapabilities**](nf-netadapteroffload-netadapteroffloadsetrsccapabilities.md).

For more info, see [NetAdapterCx hardware offloads](/windows-hardware/drivers/netcx/introduction-to-hardware-offloads).

## -see-also

[NetAdapterCx hardware offloads](/windows-hardware/drivers/netcx/introduction-to-hardware-offloads)

[**NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES**](ns-netadapteroffload-_net_adapter_offload_rsc_capabilities.md)

[**NetAdapterOffloadSetRscCapabilities**](nf-netadapteroffload-netadapteroffloadsetrsccapabilities.md)