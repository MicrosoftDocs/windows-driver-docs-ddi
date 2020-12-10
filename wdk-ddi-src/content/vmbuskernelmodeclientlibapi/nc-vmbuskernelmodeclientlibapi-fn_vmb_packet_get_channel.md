---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_PACKET_GET_CHANNEL
title: FN_VMB_PACKET_GET_CHANNEL (vmbuskernelmodeclientlibapi.h)
description: The VmbPacketGetChannel function returns the VMBus channel with which a VMBus packet is associated.
tech.root: netvista
ms.date: 05/22/2018
keywords: ["FN_VMB_PACKET_GET_CHANNEL callback function"]
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
 - FN_VMB_PACKET_GET_CHANNEL
 - vmbuskernelmodeclientlibapi/FN_VMB_PACKET_GET_CHANNEL
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - vmbuskernelmodeclientlibapi.h
api_name:
 - FN_VMB_PACKET_GET_CHANNEL
---

# FN_VMB_PACKET_GET_CHANNEL callback function


## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbPacketGetChannel</b> function returns the VMBus channel with which a VMBus packet is associated.

## -parameters

### -param PacketObject

The packet object.

## -returns

<b>VmbPacketGetChannel</b> returns a handle of the associated channel.

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

## -remarks

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also

