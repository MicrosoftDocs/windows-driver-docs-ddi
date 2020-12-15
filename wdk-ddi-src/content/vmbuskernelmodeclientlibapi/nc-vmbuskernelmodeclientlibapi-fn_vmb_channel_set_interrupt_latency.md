---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_SET_INTERRUPT_LATENCY
title: FN_VMB_CHANNEL_SET_INTERRUPT_LATENCY (vmbuskernelmodeclientlibapi.h)
description: Guest VM updates to the outgoing monitor latency for MNF interrupts.
tech.root: netvista
ms.date: 05/22/2018
keywords: ["FN_VMB_CHANNEL_SET_INTERRUPT_LATENCY callback function"]
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
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
ms.custom: RS5
f1_keywords:
 - FN_VMB_CHANNEL_SET_INTERRUPT_LATENCY
 - vmbuskernelmodeclientlibapi/FN_VMB_CHANNEL_SET_INTERRUPT_LATENCY
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - vmbuskernelmodeclientlibapi.h
api_name:
 - FN_VMB_CHANNEL_SET_INTERRUPT_LATENCY
---

# FN_VMB_CHANNEL_SET_INTERRUPT_LATENCY callback function


## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Guest VM updates to the outgoing monitor latency for MNF interrupts.

## -parameters

### -param Channel

A handle for the channel. Allocated by [**VmbChannelAllocate**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_allocate.md).

### -param Latency

The desired monitor latency in 100ns units.

### -param OriginalLatency

On success, set to the previous latency value.

## -returns

Returns STATUS_SUCCESS if the operation succeeds, or an appropriate NTSTATUS error code otherwise.

## -prototype

```cpp
//Declaration

FN_VMB_CHANNEL_SET_INTERRUPT_LATENCY FnVmbChannelSetInterruptLatency; 

// Definition

NTSTATUS FnVmbChannelSetInterruptLatency 
(
	VMBCHANNEL Channel
	UINT16 Latency
	PUINT16 OriginalLatency
)
{...}

```

## -remarks

This call is valid for opened channels, that is between the calls to [*EvtChannelOpened*](nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_opened.md) and [*EvtChannelClosed*](nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_closed.md), inclusive.

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also

