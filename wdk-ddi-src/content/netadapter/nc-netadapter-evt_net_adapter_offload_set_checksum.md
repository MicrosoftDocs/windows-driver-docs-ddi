---
UID: NC:netadapter.EVT_NET_ADAPTER_OFFLOAD_SET_CHECKSUM
title: EVT_NET_ADAPTER_OFFLOAD_SET_CHECKSUM (netadapter.h)
description: The EvtNetAdapterOffloadSetChecksum callback function is implemented by the client driver to set changes in checksum offload capabilities.
tech.root: netvista
ms.assetid: 054d73bb-6832-41f6-b654-89d29bbc1892
ms.date: 07/19/2018
keywords: ["EVT_NET_ADAPTER_OFFLOAD_SET_CHECKSUM callback function"]
f1_keywords:
 - "netadapter/EVT_NET_ADAPTER_OFFLOAD_SET_CHECKSUM"
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
- apiref
api_type: 
- UserDefined
api_location: 
- netadapter.h
api_name: 
- EVT_NET_ADAPTER_OFFLOAD_SET_CHECKSUM
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# EVT_NET_ADAPTER_OFFLOAD_SET_CHECKSUM callback function

## -description



The *EvtNetAdapterOffloadSetChecksum* callback function is implemented by the client driver to set changes in active checksum offload capabilities.

## -prototype

```C++
//Declaration

EVT_NET_ADAPTER_OFFLOAD_SET_CHECKSUM EvtNetAdapterOffloadSetChecksum; 

// Definition

VOID EvtNetAdapterOffloadSetChecksum 
(
	NETADAPTER 	Adapter,
	NETOFFLOAD	Offload
)
{...}

```

## -parameters

### -param Adapter

A handle to a NETADAPTER object the client driver previously created with a call to [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

### -param Offload

A handle to a NETOFFLOAD object that describes the adapter's offload capabilities.

## -remarks

Register your implementation of this callback function by setting the appropriate parameter when calling [**NetAdapterOffloadSetChecksumCapabilities**](nf-netadapter-netadapteroffloadsetchecksumcapabilities.md).

For an example implementation of this callback, see [NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads).

## -see-also

[NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[**NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES**](ns-netadapter-_net_adapter_offload_checksum_capabilities.md)

[**NetAdapterOffloadSetChecksumCapabilities**](nf-netadapter-netadapteroffloadsetchecksumcapabilities.md)
