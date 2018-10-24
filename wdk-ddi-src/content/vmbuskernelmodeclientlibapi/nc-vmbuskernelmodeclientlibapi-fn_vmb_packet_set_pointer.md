---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_PACKET_SET_POINTER
title: FN_VMB_PACKET_SET_POINTER
author: windows-driver-content
description: The VmbPacketSetPointer function saves an arbitrary pointer in the packet context.
tech.root: netvista
ms.assetid: 5c6d8399-50ff-466c-9942-8b5232b841ad
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
-	apiref
api_type: 
-	UserDefined
api_location: 
-	vmbuskernelmodeclientlibapi.h
api_name: 
-	FN_VMB_PACKET_SET_POINTER
product:
-	Windows
targetos: Windows
---

# FN_VMB_PACKET_SET_POINTER callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbPacketSetPointer</b> function saves an arbitrary pointer in the packet
context.

## -prototype

```cpp
//Declaration

FN_VMB_PACKET_SET_POINTER FnVmbPacketSetPointer; 

// Definition

VOID FnVmbPacketSetPointer 
(
	VMBPACKET PacketObject
	PVOID Pointer
)
{...}

```

## -parameters

### -param PacketObject

A handle for a VMBus packet.

### -param Pointer

 An arbitrary pointer to save in the context of the packet.

## -returns

This function does not return a value.

## -remarks

This function is intended to offer a more efficient way to retrieve the context of a client driver.

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also
