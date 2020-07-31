---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_PACKET_DEFER_TO_PASSIVE
title: FN_VMB_CHANNEL_PACKET_DEFER_TO_PASSIVE (vmbuskernelmodeclientlibapi.h)
description: The VmbChannelPacketDeferToPassive function is called by the client driver to defer a packet passed to it by the EvtVmbChannelProcessPacket callback function.
tech.root: netvista
ms.assetid: 7226008d-7c72-4f80-a100-3441c199ba48
ms.date: 05/21/2018
keywords: ["FN_VMB_CHANNEL_PACKET_DEFER_TO_PASSIVE callback function"]
f1_keywords:
 - "vmbuskernelmodeclientlibapi/FN_VMB_CHANNEL_PACKET_DEFER_TO_PASSIVE"
 - "FN_VMB_CHANNEL_PACKET_DEFER_TO_PASSIVE"
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
topic_type: 
- apiref
api_type: 
- UserDefined
api_location: 
- vmbuskernelmodeclientlibapi.h
api_name: 
- FN_VMB_CHANNEL_PACKET_DEFER_TO_PASSIVE
targetos: Windows
ms.custom: RS5
---

# FN_VMB_CHANNEL_PACKET_DEFER_TO_PASSIVE callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelPacketDeferToPassive</b> function is called by the client driver to defer a packet
passed to it by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_process_packet">EvtVmbChannelProcessPacket</a> callback function.  

## -prototype

```cpp
//Declaration

FN_VMB_CHANNEL_PACKET_DEFER_TO_PASSIVE FnVmbChannelPacketDeferToPassive; 

// Definition

VOID FnVmbChannelPacketDeferToPassive 
(
	VMBPACKETCOMPLETION PacketCompletionContext
)
{...}

```

## -parameters

### -param PacketCompletionContext

A  handle that identifies the incoming packet and is used to refer to the packet
once processing is finished.  

## -remarks

A deferred packet goes back onto the parsing queue. It is guaranteed to be
parsed again at PASSIVE_LEVEL.


This routine is designed to only be called in-line from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_process_packet">EvtVmbChannelProcessPacket</a>.

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_process_packet">EvtVmbChannelProcessPacket</a>
