---
UID: NF:netadapteroffload.NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES_INIT
title: NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES_INIT function (netadapteroffload.h)
description: The NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES_INIT function initializes a NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES structure.
tech.root: netvista
ms.assetid: 1df09a2f-d816-407a-8759-142f569f0f57
ms.date: 10/15/2020
keywords: ["NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES_INIT function"]
ms.keywords: NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES_INIT
req.header: netadapteroffload.h
req.include-header: netadaptercx.h 
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: Any level as long as target memory is resident
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: Vb
f1_keywords:
 - NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES_INIT
 - netadapteroffload/NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES_INIT
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapteroffload.h
api_name:
 - NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES_INIT
product:
 - Windows
---

# NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES_INIT function


## -description

The **NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES_INIT** function initializes a [**NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES**](../netadapteroffload/ns-netadapteroffload-_net_adapter_offload_rsc_capabilities.md) structure.

## -parameters

### -param RscCapabilities

[_Out_] A pointer to a driver-allocated [**NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES**](../netadapteroffload/ns-netadapteroffload-_net_adapter_offload_rsc_capabilities.md) structure.

### -param Layer3Flags

[_In_] Flags specifying the layer 3 protocols that the NIC can successfully perform RSC on.

### -param Layer4Flags

[_In_] Flags specifying the layer 4 protocols that the NIC can successfully perform RSC on.

### -param EvtAdapterOffloadSetRsc

[_In_] A pointer to the client driver's implementation of the [*EVT_NET_ADAPTER_OFFLOAD_SET_RSC*](../netadapteroffload/nc-netadapteroffload-evt_net_adapter_offload_set_rsc.md) callback function.

## -returns

This function does not return a value.

## -remarks

The client driver calls **NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES_INIT** to initialize a [**NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES**](ns-netadapteroffload-_net_adapter_offload_rsc_capabilities.md) structure. The driver passes the initialized **NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES** structure as a parameter to the [**NetAdapterOffloadSetRscCapabilities**](nf-netadapteroffload-netadapteroffloadsetrsccapabilities.md) function to register it.

To see an example of how a client driver might set up its RSC hardware offload capabilities, see [Receive Segment Coalescing offload](/windows-hardware/drivers/netcx/rsc-offloads).

## -see-also

[Receive Segment Coalescing offload](/windows-hardware/drivers/netcx/rsc-offloads)

[**NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES**](ns-netadapteroffload-_net_adapter_offload_rsc_capabilities.md)

[**NetAdapterOffloadSetRscCapabilities**](nf-netadapteroffload-netadapteroffloadsetrsccapabilities.md)