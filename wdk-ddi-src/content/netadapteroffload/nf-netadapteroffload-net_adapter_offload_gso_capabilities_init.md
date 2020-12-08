---
UID: NF:netadapteroffload.NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES_INIT
title: NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES_INIT function (netadapteroffload.h)
description: The NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES_INIT function initializes a NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES structure.
tech.root: netvista
ms.date: 10/09/2020
keywords: ["NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES_INIT function"]
f1_keywords:
 - "netadapteroffload/NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES_INIT"
ms.keywords: NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES_INIT
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
topic_type: 
- apiref
api_type: 
- LibDef
api_location: 
- netadaptercxstub.lib
api_name: 
- NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES_INIT
product:
- Windows
targetos: Windows
ms.custom: Fe
---

# NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES_INIT function


## -description

> [!WARNING]
> Some information in this topic relates to pre-released product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 2004.
>
> Currently, NetAdapterCx client drivers cannot be certified.

The **NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES_INIT** function initializes a [**NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES**](ns-netadapteroffload-_net_adapter_offload_gso_capabilities.md) structure.

## -parameters

### -param GsoCapabilities

[_Out_] A pointer to a driver-allocated [**NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES**](../netadapteroffload/ns-netadapteroffload-_net_adapter_offload_gso_capabilities.md) structure.

### -param Layer3Flags

[_In_] Flags specifying the layer 3 protocols and variations contained in packets that the NIC can successfully segment.

### -param Layer4Flags

[_In_] Flags specifying the layer 4 protocols and variations contained in packets that the NIC can successfully segment.

### -param MaximumOffloadSize

[_In_] The maximum bytes of user data that the transport can pass to the NIC driver in a single packet.

### -param MinimumSegmentCount

[_In_] The minimum number of segments by which a large TCP packet must be divisible before the transport can offload it to the hardware for segmentation.

### -param EvtAdapterOffloadSetGso

[_In_] A pointer to the client driver's implementation of the [*EVT_NET_ADAPTER_OFFLOAD_SET_GSO*](nc-netadapteroffload-evt_net_adapter_offload_set_gso.md) callback function.

## -remarks

The client driver calls **NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES_INIT** to initialize a [**NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES**](ns-netadapteroffload-_net_adapter_offload_gso_capabilities.md) structure. The driver passes the initialized **NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES** structure as a parameter to the [**NetAdapterOffloadSetGsoCapabilities**](nf-netadapteroffload-netadapteroffloadsetgsocapabilities.md) function to register it.

## -see-also

[Generic Segmentation Offload](/windows-hardware/drivers/netcx/gso-offload)

[*EVT_NET_ADAPTER_OFFLOAD_SET_GSO*](nc-netadapteroffload-evt_net_adapter_offload_set_gso.md)

[**NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES**](ns-netadapteroffload-_net_adapter_offload_gso_capabilities.md)

[**NetAdapterOffloadSetGsoCapabilities**](nf-netadapteroffload-netadapteroffloadsetgsocapabilities.md)
