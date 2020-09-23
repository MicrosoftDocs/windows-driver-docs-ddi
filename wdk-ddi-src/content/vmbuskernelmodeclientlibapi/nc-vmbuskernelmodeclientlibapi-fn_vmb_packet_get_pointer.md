---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_PACKET_GET_POINTER
title: FN_VMB_PACKET_GET_POINTER (vmbuskernelmodeclientlibapi.h)
description: The VmbPacketGetPointer function retrieves a pointer that was previously saved by using the VmbPacketSetPointer function.
tech.root: netvista
ms.assetid: 51c40032-5700-49d8-ba21-a03739e9dd3b
ms.date: 05/22/2018
keywords: ["FN_VMB_PACKET_GET_POINTER callback function"]
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
 - FN_VMB_PACKET_GET_POINTER
 - vmbuskernelmodeclientlibapi/FN_VMB_PACKET_GET_POINTER
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - vmbuskernelmodeclientlibapi.h
api_name:
 - FN_VMB_PACKET_GET_POINTER
---

# FN_VMB_PACKET_GET_POINTER callback function


## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbPacketGetPointer</b> function retrieves a pointer that was previously
saved by using the <a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbpacketsetpointer">VmbPacketSetPointer</a> function.

## -parameters

### -param PacketObject 

The handle of a packet object.

## -returns

<b>VmbPacketGetPointer</b> returns the value previously saved by using <a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbpacketsetpointer">VmbPacketSetPointer</a>.

## -prototype

```cpp
//Declaration

FN_VMB_PACKET_GET_POINTER FnVmbPacketGetPointer; 

// Definition

PVOID FnVmbPacketGetPointer 
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

<a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbpacketsetpointer">VmbPacketSetPointer</a>