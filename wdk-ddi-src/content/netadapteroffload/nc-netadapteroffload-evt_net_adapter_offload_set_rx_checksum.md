---
UID: NC:netadapteroffload.EVT_NET_ADAPTER_OFFLOAD_SET_RX_CHECKSUM
title: EVT_NET_ADAPTER_OFFLOAD_SET_RX_CHECKSUM (netadapteroffload.h)
description: The client driver implements the EvtNetAdapterOffloadSetRxChecksum callback function to set changes in Rx checksum offload capabilities.
tech.root: netvista
ms.date: 10/06/2020
keywords: ["EVT_NET_ADAPTER_OFFLOAD_SET_RX_CHECKSUM callback function"]
req.header: netadapteroffload.h
req.include-header: netadaptercx.h
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
targetos: Windows
ms.custom: Fe
f1_keywords:
 - EVT_NET_ADAPTER_OFFLOAD_SET_RX_CHECKSUM
 - netadapteroffload/EVT_NET_ADAPTER_OFFLOAD_SET_RX_CHECKSUM
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
---

# EVT_NET_ADAPTER_OFFLOAD_SET_RX_CHECKSUM callback function


## -description

> [!WARNING]
> Some information in this topic relates to pre-released product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 2004.
>
> Currently, NetAdapterCx client drivers cannot be certified.

The client driver implements the *EvtNetAdapterOffloadSetRxChecksum* callback function to query changes in active Rx checksum offload capabilities and update the hardware accordingly.

## -parameters

### -param Adapter

[_In_] A handle to a NETADAPTER object the client driver previously created with a call to [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md).

### -param Offload 

[_In_] A handle to a NETOFFLOAD object that describes the adapter's offload capabilities.

## -remarks

Register your implementation of this callback function by setting the appropriate parameter when calling [**NetAdapterOffloadSetRxChecksumCapabilities**](nf-netadapteroffload-netadapteroffloadsetrxchecksumcapabilities.md).

For an example implementation of this callback, [Checksum Offload](/windows-hardware/drivers/netcx/checksum-offload).

## -see-also

[Checksum Offload](/windows-hardware/drivers/netcx/checksum-offload)

[**NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES**](ns-netadapteroffload-_net_adapter_offload_rx_checksum_capabilities.md)

[**NetAdapterOffloadSetRxChecksumCapabilities**](nf-netadapteroffload-netadapteroffloadsetrxchecksumcapabilities.md)

