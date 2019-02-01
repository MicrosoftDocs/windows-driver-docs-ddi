---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_PACKET_COMPLETE
title: FN_VMB_CHANNEL_PACKET_COMPLETE (vmbuskernelmodeclientlibapi.h)
description: The VmbChannelPacketComplete function cleans up any outstanding memory mappings, releases any buffers in use, and, if the opposite endpoint requested a completion packet, sends a completion packet.
tech.root: netvista
ms.assetid: 371b8ad4-4777-427c-9b9f-6c9c07bb9c3d
ms.date: 05/21/2018
ms.topic: callback
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
-	apiref
api_type: 
-	UserDefined
api_location: 
-	vmbuskernelmodeclientlibapi.h
api_name: 
-	FN_VMB_CHANNEL_PACKET_COMPLETE
product:
-	Windows
targetos: Windows
ms.custom: RS5
---

# FN_VMB_CHANNEL_PACKET_COMPLETE callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelPacketComplete</b>  function cleans up any
outstanding memory mappings, releases any buffers in use, and, if the opposite endpoint requested a completion packet, sends a
completion packet. 

## -prototype

```cpp
//Declaration

FN_VMB_CHANNEL_PACKET_COMPLETE FnVmbChannelPacketComplete; 

// Definition

VOID FnVmbChannelPacketComplete 
(
	VMBPACKETCOMPLETION PacketCompletionContext
	PVOID PacketCompletionBuffer
	UINT32 BufSize
)
{...}

```

## -parameters

### -param PacketCompletionContext

A handle that identifies the incoming packet and is used to refer to the packet
once processing is finished. 

### -param PacketCompletionBuffer

A buffer of completion data to be sent back to the originating endpoint.  Although this usually contains just a status value, the contents are up to the client driver.

### -param BufSize

The size, in bytes, of the completion buffer.

## -returns

This function does not return a value.

## -remarks

This function is called when the client driver is finished
processing a packet.  This function may be called directly from the packet parsing function
or it may be called later. 

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also
