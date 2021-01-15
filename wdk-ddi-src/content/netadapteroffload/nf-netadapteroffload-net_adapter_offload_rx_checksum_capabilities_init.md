---
UID: NF:netadapteroffload.NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES_INIT
title: NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES_INIT function (netadapteroffload.h)
description: The NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES_INIT function initializes a NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES structure.
tech.root: netvista
ms.date: 10/06/2020
keywords: ["NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES_INIT function"]
ms.keywords: NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES_INIT
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.29
req.umdf-ver: 
req.lib: netadaptercxstub.lib
req.dll: 
req.irql: 
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
 - NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES_INIT
 - netadapteroffload/NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES_INIT
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - netadaptercxstub.lib
api_name:
 - NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES_INIT
product:
 - Windows
---

# NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES_INIT function


## -description

> [!WARNING]
> Some information in this topic relates to pre-released product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 2004.
>
> Currently, NetAdapterCx client drivers cannot be certified.

The **NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES_INIT** function initializes a [**NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES**](ns-netadapteroffload-_net_adapter_offload_rx_checksum_capabilities.md) structure.

## -parameters

### -param Capabilities

[_Out_] A pointer to a driver-allocated [**NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES**](ns-netadapteroffload-_net_adapter_offload_rx_checksum_capabilities.md) structure.

### -param EvtAdapterOffloadSetRxChecksum

[_In_] A pointer to the client driver's implementation of the [*EVT_NET_ADAPTER_OFFLOAD_SET_RX_CHECKSUM*](nc-netadapteroffload-evt_net_adapter_offload_set_rx_checksum.md) callback function.

## -remarks

The client driver calls **NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES_INIT** to initialize a [**NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES**](ns-netadapteroffload-_net_adapter_offload_rx_checksum_capabilities.md) structure. The driver passes the initialized **NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES** structure as a parameter to the [**NetAdapterOffloadSetRxChecksumCapabilities**](nf-netadapteroffload-netadapteroffloadsetrxchecksumcapabilities.md) function to register it.

## -see-also

[Checksum Offload](/windows-hardware/drivers/netcx/checksum-offload)

[*EVT_NET_ADAPTER_OFFLOAD_SET_RX_CHECKSUM*](nc-netadapteroffload-evt_net_adapter_offload_set_rx_checksum.md)

[**NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES**](ns-netadapteroffload-_net_adapter_offload_rx_checksum_capabilities.md)

[**NetAdapterOffloadSetRxChecksumCapabilities**](nf-netadapteroffload-netadapteroffloadsetrxchecksumcapabilities.md)

