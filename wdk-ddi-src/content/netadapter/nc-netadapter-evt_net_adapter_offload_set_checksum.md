---
UID: NC:netadapter.EVT_NET_ADAPTER_OFFLOAD_SET_CHECKSUM
title: EVT_NET_ADAPTER_OFFLOAD_SET_CHECKSUM (netadapter.h)
description: The EvtNetAdapterOffloadSetChecksum callback function is implemented by the client driver to set changes in checksum offload capabilities.
tech.root: netvista
ms.date: 07/19/2018
keywords: ["EVT_NET_ADAPTER_OFFLOAD_SET_CHECKSUM callback function"]
req.header: netadapter.h
req.include-header: netadaptercx.h 
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
targetos: Windows
ms.custom: RS5
f1_keywords:
 - EVT_NET_ADAPTER_OFFLOAD_SET_CHECKSUM
 - netadapter/EVT_NET_ADAPTER_OFFLOAD_SET_CHECKSUM
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - netadapter.h
api_name:
 - EVT_NET_ADAPTER_OFFLOAD_SET_CHECKSUM
---

# EVT_NET_ADAPTER_OFFLOAD_SET_CHECKSUM callback function


## -description

> [!NOTE]
> The *EvtNetAdapterOffloadSetChecksum* callback function is deprecated in NetAdapterCx 2.1 and later. For more information on current checksum offload functions, see [Checksum offload](/windows-hardware/drivers/netcx/checksum-offload).

The *EvtNetAdapterOffloadSetChecksum* callback function is implemented by the client driver to set changes in active checksum offload capabilities.

## -parameters

### -param Adapter

A handle to a NETADAPTER object the client driver previously created with a call to [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

### -param Offload

A handle to a NETOFFLOAD object that describes the adapter's offload capabilities.

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

## -remarks

Register your implementation of this callback function by setting the appropriate parameter when calling [**NetAdapterOffloadSetChecksumCapabilities**](nf-netadapter-netadapteroffloadsetchecksumcapabilities.md).

For an example implementation of this callback, see [NetAdapterCx hardware offloads](/windows-hardware/drivers/netcx/introduction-to-hardware-offloads).

## -see-also

[NetAdapterCx hardware offloads](/windows-hardware/drivers/netcx/introduction-to-hardware-offloads)

[**NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES**](ns-netadapter-_net_adapter_offload_checksum_capabilities.md)

[**NetAdapterOffloadSetChecksumCapabilities**](nf-netadapter-netadapteroffloadsetchecksumcapabilities.md)
