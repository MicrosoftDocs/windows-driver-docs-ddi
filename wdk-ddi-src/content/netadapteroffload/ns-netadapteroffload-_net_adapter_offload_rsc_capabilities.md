---
UID: NS:netadapteroffload._NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES
title: NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES (netadapteroffload.h)
description: The NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES structure describes a network interface card (NIC)'s capabilities for receive segment coalescence (RSC).
tech.root: netvista
ms.date: 10/15/2020
keywords: ["NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES structure"]
ms.keywords: NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES, NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES,
req.header: netadapteroffload.h
req.include-header: netadaptercx.h 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES
targetos: Windows
ms.custom: Vb
f1_keywords:
 - _NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES
 - netadapteroffload/_NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES
 - NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES
 - netadapteroffload/NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapteroffload.h
api_name:
 - NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES
product:
 - Windows
---

# NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES structure


## -description

> [!WARNING]
> Some information in this topic relates to pre-released product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 2004.
>
> Currently, NetAdapterCx client drivers cannot be certified.

The **NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES** structure describes a network interface card (NIC)'s capabilities for receive segment coalescence (RSC).

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field Layer3Flags

 
Flags specifying the layer 3 protocols that the NIC can successfully perform RSC on. `NetAdapterOffloadLayer3FlagIPv4NoOptions` and `NetAdapterOffloadLayer3FlagIPv6NoExtensions` are the only valid values.

### -field Layer4Flags

Flags specifying the layer 4 protocols that the NIC can successfully perform RSC on. `NetAdapterOffloadLayer4FlagTcpNoOptions` is the only valid value. Layer 3 flags must be set if the `NetAdapterOffloadLayer4FlagTcpNoOptions` flag is set.

### -field TcpTimestampOption

Optional. A flag specifying whether the hardware can perform RSC on packets with a timestamp.

### -field EvtAdapterOffloadSetRsc

A pointer to the client driver's implementation of the [*EVT_NET_ADAPTER_OFFLOAD_SET_RSC*](nc-netadapteroffload-evt_net_adapter_offload_set_rsc.md) callback function.

## -remarks

Call [**NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES_INIT**](nf-netadapteroffload-net_adapter_offload_rsc_capabilities_init.md) to initialize this structure. The client driver passes an initialized  **NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES** structure as a parameter to [**NetAdapterOffloadSetRscCapabilities**](nf-netadapteroffload-netadapteroffloadsetrsccapabilities.md).

To see an example of how a client driver might set up its RSC hardware offload capabilities, see [Receive Segment Coalescing offload](/windows-hardware/drivers/netcx/rsc-offload).

## -see-also

[Receive Segment Coalescing offload](/windows-hardware/drivers/netcx/rsc-offload)

[**NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES_INIT**](nf-netadapteroffload-net_adapter_offload_rsc_capabilities_init.md)

[**NetAdapterOffloadSetRscCapabilities**](nf-netadapteroffload-netadapteroffloadsetrsccapabilities.md)

[*EVT_NET_ADAPTER_OFFLOAD_SET_RSC*](nc-netadapteroffload-evt_net_adapter_offload_set_rsc.md) 
