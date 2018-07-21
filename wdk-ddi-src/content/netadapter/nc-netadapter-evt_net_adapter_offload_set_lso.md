---
UID: NC:netadapter.EVT_NET_ADAPTER_OFFLOAD_SET_LSO
title: EVT_NET_ADAPTER_OFFLOAD_SET_LSO
author: windows-driver-content
description: The EvtNetAdapterOffloadSetLso callback function is implemented by the client driver to set changes in large send offload (LSO) offload capabilities.
ms.assetid: 7c11be49-4d85-49c4-9416-47da1214fc1b
ms.author: windowsdriverdev
ms.date: 07/20/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: netadapter.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
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
-	apiref
api_type: 
-	UserDefined
api_location: 
-	netadapter.h
api_name: 
-	EVT_NET_ADAPTER_OFFLOAD_SET_LSO
product: Windows
targetos: Windows
---

# EVT_NET_ADAPTER_OFFLOAD_SET_LSO callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The *EvtNetAdapterOffloadSetLso* callback function is implemented by the client driver to set changes in active large send offload (LSO) offload capabilities.

## -prototype

```C++
//Declaration

EVT_NET_ADAPTER_OFFLOAD_SET_LSO EvtNetAdapterOffloadSetLso; 

// Definition

VOID EvtNetAdapterOffloadSetLso 
(
	NETADAPTER Adapter
	PNET_ADAPTER_OFFLOAD_LSO_CAPABILITIES ActiveCapabilities
)
{...}

```

## -parameters

### -param Adapter

A handle to a NETADAPTER object the client driver previously created with a call to [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

### -param ActiveCapabilities 

A pointer to a [**NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES**](ns-netadapter-_net_adapter_offload_lso_capabilities.md) structure that describes the hardware's updated active LSO offload capabilities.

## -returns

This callback function does not return a value.

## -remarks

Register your implementation of this callback function by setting the appropriate parameter when calling [**NetAdapterOffloadSetLsoCapabilities**](nf-netadapter-netadapteroffloadsetlsocapabilities.md).

### Example

In this callback, client drivers update the active hardware LSO offload capabilities as provided in *ActiveCapabilities*.

```C++
VOID
MyEvtAdapterOffloadSetLso(
	NETADAPTER NetAdapter,
	PNET_ADAPTER_OFFLOAD_LSO_CAPABILITIES ActiveCapabilities
)
{
	PMY_NET_ADAPTER_CONTEXT adapterContext = MyGetNetAdapterContext(NetAdapter);

	// Store the updated information in the context
	adapterContext->HardwareIpv4Lso = ActiveCapabilities->IPv4;
	adapterContext->HardwareIpv6Lso = ActiveCapabilities->IPv6;
	adapterContext->HardwareLsoMaxOffloadSize = ActiveCapabilities->MaximumOffloadSize;
	adapterContext->HardwareLsoMinSegCount = ActiveCapabilities->MinimumSegmentCount;

	// Update the new hardware lso offload capabilities
	MyUpdateHardwareLso(adapterContext);
}
```

## -see-also

[NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[**NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES**](ns-netadapter-_net_adapter_offload_lso_capabilities.md)

[**NetAdapterOffloadSetLsoCapabilities**](nf-netadapter-netadapteroffloadsetlsocapabilities.md)