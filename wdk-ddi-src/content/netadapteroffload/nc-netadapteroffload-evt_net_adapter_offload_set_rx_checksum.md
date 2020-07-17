---
UID: NC:netadapteroffload.EVT_NET_ADAPTER_OFFLOAD_SET_RX_CHECKSUM
title: EVT_NET_ADAPTER_OFFLOAD_SET_RX_CHECKSUM (netadapteroffload.h)
description: The EvtNetAdapterOffloadSetRxChecksum callback function is implemented by the client driver to set changes in Rx checksum offload capabilities.
tech.root: netvista
ms.assetid: 7c11be49-4d85-49c4-9416-47da1214fc1b
ms.date: 01/17/2019
keywords: ["EVT_NET_ADAPTER_OFFLOAD_SET_RX_CHECKSUM callback function"]
f1_keywords:
 - "netadapteroffload/EVT_NET_ADAPTER_OFFLOAD_SET_RX_CHECKSUM"
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
- netadapteroffload.h
api_name: 
- EVT_NET_ADAPTER_OFFLOAD_SET_RX_CHECKSUM
product:
- Windows
targetos: Windows
ms.custom: 19H1
---

# EVT_NET_ADAPTER_OFFLOAD_SET_RX_CHECKSUM callback function

## -description



The *EvtNetAdapterOffloadSetRxChecksum* callback function is implemented by the client driver to set changes in active Rx checksum offload capabilities.

## -prototype

```C++
//Declaration

EVT_NET_ADAPTER_OFFLOAD_SET_RX_CHECKSUM EvtNetAdapterOffloadSetRxChecksum; 

// Definition

VOID EvtNetAdapterOffloadSetRxChecksum
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

## -remarks

Register your implementation of this callback function by setting the appropriate parameter when calling [**NetAdapterOffloadSetRxChecksumCapabilities**](nf-netadapteroffload-netadapteroffloadsettchecksumcapabilities.md).

For an example implementation of this callback, see [NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads).

## -see-also

[NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[**NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES**](ns-netadapteroffload-_net_adapter_offload_rx_checksum_capabilities.md)

[**NetAdapterOffloadSetRxChecksumCapabilities**](nf-netadapteroffload-netadapteroffloadsetrxchecksumcapabilities.md)
