---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_PACKET_GET_CHANNEL
title: FN_VMB_PACKET_GET_CHANNEL (vmbuskernelmodeclientlibapi.h)
description: The VmbPacketGetChannel function returns the VMBus channel with which a VMBus packet is associated.
tech.root: netvista
ms.assetid: 3032635f-c7f0-42f7-9c44-5077b23c0f75
ms.date: 05/22/2018
keywords: ["FN_VMB_PACKET_GET_CHANNEL callback function"]
f1_keywords:
 - "vmbuskernelmodeclientlibapi/FN_VMB_PACKET_GET_CHANNEL"
 - "FN_VMB_PACKET_GET_CHANNEL"
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
- FN_VMB_PACKET_GET_CHANNEL
targetos: Windows
ms.custom: RS5
---

# FN_VMB_PACKET_GET_CHANNEL callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbPacketGetChannel</b> function returns the VMBus channel with which a VMBus packet is associated.

## -prototype

```cpp
//Declaration

FN_VMB_PACKET_GET_CHANNEL FnVmbPacketGetChannel; 

// Definition

VMBCHANNEL FnVmbPacketGetChannel 
(
	VMBPACKET PacketObject
)
{...}

```

## -parameters

### -param PacketObject

The packet object.

## -returns

<b>VmbPacketGetChannel</b> returns a handle of the associated channel.

## -remarks

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also
