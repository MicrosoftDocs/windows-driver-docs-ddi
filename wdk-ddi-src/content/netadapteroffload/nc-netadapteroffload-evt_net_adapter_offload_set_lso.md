---
UID: NC:netadapteroffload.EVT_NET_ADAPTER_OFFLOAD_SET_LSO
title: EVT_NET_ADAPTER_OFFLOAD_SET_LSO (netadapteroffload.h)
description: The EvtNetAdapterOffloadSetLso callback function is implemented by the client driver to set changes in large send offload (LSO) offload capabilities.
tech.root: netvista
ms.assetid: 7c11be49-4d85-49c4-9416-47da1214fc1b
ms.date: 01/17/2019
ms.topic: callback
f1_keywords:
 - "netadapteroffload/EVT_NET_ADAPTER_OFFLOAD_SET_LSO"
req.header: netadapteroffload.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.29
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
-	netadapteroffload.h
api_name: 
- EVT_NET_ADAPTER_OFFLOAD_SET_LSO
product:
- Windows
targetos: Windows
ms.custom: 19H1
---

# EVT_NET_ADAPTER_OFFLOAD_SET_LSO callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The *EvtNetAdapterOffloadSetLso* callback function is implemented by the client driver to set changes in active large send offload (LSO) offload capabilities.

## -prototype

```C++
//Declaration

EVT_NET_ADAPTER_OFFLOAD_SET_LSO EvtNetAdapterOffloadSetLso; 

// Definition

VOID EvtNetAdapterOffloadSetLso 
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

Register your implementation of this callback function by setting the appropriate parameter when calling [**NetAdapterOffloadSetLsoCapabilities**](nf-netadapteroffload-netadapteroffloadsetlsocapabilities.md).

For an example implementation of this callback, see [NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads).

## -see-also

[NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[**NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES**](ns-netadapteroffload-_net_adapter_offload_lso_capabilities.md)

[**NetAdapterOffloadSetLsoCapabilities**](nf-netadapteroffload-netadapteroffloadsetlsocapabilities.md)
