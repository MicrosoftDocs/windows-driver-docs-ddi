---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_SIZEOF_PACKET
title: FN_VMB_CHANNEL_SIZEOF_PACKET (vmbuskernelmodeclientlibapi.h)
description: The VmbChannelSizeofPacket function calculates the necessary size for buffers to be used with the VmbPacketInitialize function.
tech.root: netvista
ms.assetid: 05f275dd-cde2-425f-ac13-57b11c8affdf
ms.date: 05/22/2018
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
- apiref
api_type: 
- UserDefined
api_location: 
- vmbuskernelmodeclientlibapi.h
api_name: 
- FN_VMB_CHANNEL_SIZEOF_PACKET
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# FN_VMB_CHANNEL_SIZEOF_PACKET callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelSizeofPacket</b> function calculates the necessary size for buffers to be used with
the <a href="https://msdn.microsoft.com/D5D8D994-0BB6-44FC-A696-F2E0264445C1">VmbPacketInitialize</a> function.

## -prototype

```cpp
//Declaration

FN_VMB_CHANNEL_SIZEOF_PACKET FnVmbChannelSizeofPacket; 

// Definition

UINT32 FnVmbChannelSizeofPacket 
(
	VMBCHANNEL Channel
)
{...}

```

## -parameters

### -param Channel

A handle for a channel.

## -returns

The necessary buffer size, in bytes.

## -remarks

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also

<a href="https://msdn.microsoft.com/D5D8D994-0BB6-44FC-A696-F2E0264445C1">VmbPacketInitialize</a>
