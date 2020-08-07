---
UID: NC:netadapteroffload.EVT_NET_ADAPTER_OFFLOAD_SET_TX_CHECKSUM
title: EVT_NET_ADAPTER_OFFLOAD_SET_TX_CHECKSUM (netadapteroffload.h)
description: The EvtNetAdapterOffloadSetTxChecksum callback function is implemented by the client driver to set changes in Tx checksum offload capabilities.
tech.root: netvista
ms.assetid: 
ms.date: 08/10/2020
keywords: ["EVT_NET_ADAPTER_OFFLOAD_SET_TX_CHECKSUM callback function"]
f1_keywords:
 - "netadapteroffload/EVT_NET_ADAPTER_OFFLOAD_SET_TX_CHECKSUM"
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
- EVT_NET_ADAPTER_OFFLOAD_SET_TX_CHECKSUM
product:
- Windows
targetos: Windows
ms.custom: Fe
---

# EVT_NET_ADAPTER_OFFLOAD_SET_TX_CHECKSUM callback function

## -description

The *EvtNetAdapterOffloadSetTxChecksum* callback function is implemented by the client driver to query changes in active Tx checksum offload capabilities and update the hardware settings accordingly.

## -prototype

```C++
//Declaration

EVT_NET_ADAPTER_OFFLOAD_SET_TX_CHECKSUM EvtNetAdapterOffloadSetTxChecksum; 

// Definition

VOID EvtNetAdapterOffloadSetTxChecksum
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

Register your implementation of this callback function by setting the appropriate parameter when calling [**NetAdapterOffloadSetTxChecksumCapabilities**](nf-netadapteroffload-netadapteroffloadsettchecksumcapabilities.md).

For an example implementation of this callback, see [NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads).

## -see-also

[NetAdapterCx hardware offloads](/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[Checksum Offload](/windows-hardware/drivers/netcx/checksum-offload)

[**NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES**](ns-netadapteroffload-_net_adapter_offload_tx_checksum_capabilities.md)

[**NetAdapterOffloadSetTxChecksumCapabilities**](nf-netadapteroffload-netadapteroffloadsettxchecksumcapabilities.md)
