---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_PACKET_RESTORE
title: FN_VMB_PACKET_RESTORE
author: windows-driver-content
description: The VmbPacketRestore function restores packet from a buffer that contains saved packet context.
tech.root: netvista
ms.assetid: 2bb4f7b2-a6e7-4a11-a5ca-bfd7db47037a
ms.author: windowsdriverdev
ms.date: 05/22/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	FN_VMB_PACKET_RESTORE
product:
-	Windows
targetos: Windows
---

# FN_VMB_PACKET_RESTORE callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbPacketRestore</b> function restores packet from a buffer that contains saved packet
context.

## -prototype

```cpp
//Declaration

FN_VMB_PACKET_RESTORE FnVmbPacketRestore; 

// Definition

NTSTATUS FnVmbPacketRestore 
(
	__drv_aliasesMem VMBPACKET PacketObject
	PVOID Buffer
	ULONG BufferSize
)
{...}

```

## -parameters

### -param PacketObject

This is a handle of a VMBus packet.

### -param Buffer

Pointer to buffer that contains previously saved context.

### -param BufferSize

The size, in bytes, of buffer.

## -returns

Returns STATUS_SUCCESS if the operation succeeds, or an appropriate NTSTATUS error code otherwise.

## -remarks

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a server-only function accessed from the [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md) structure. 
>
> For more information, see the Remarks section of [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md).

## -see-also
