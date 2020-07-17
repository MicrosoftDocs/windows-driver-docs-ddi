---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_GET_POINTER
title: FN_VMB_CHANNEL_GET_POINTER (vmbuskernelmodeclientlibapi.h)
description: The VmbChannelGetPointer function lets a client driver retrieve a pointer that was previously saved by using the VmbPacketSetPointer function.
tech.root: netvista
ms.assetid: 58de32e6-224f-4c54-b07e-9a8494d7ac63
ms.date: 05/21/2018
keywords: ["FN_VMB_CHANNEL_GET_POINTER callback function"]
f1_keywords:
 - "vmbuskernelmodeclientlibapi/FN_VMB_CHANNEL_GET_POINTER"
 - "FN_VMB_CHANNEL_GET_POINTER"
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
- FN_VMB_CHANNEL_GET_POINTER
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# FN_VMB_CHANNEL_GET_POINTER callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelGetPointer</b> function lets a client driver retrieve a pointer that was previously saved by using the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbpacketsetpointer">VmbPacketSetPointer</a> function.

## -prototype

```cpp
//Declaration

FN_VMB_CHANNEL_GET_POINTER FnVmbChannelGetPointer; 

// Definition

PVOID FnVmbChannelGetPointer 
(
	VMBCHANNEL Channel
)
{...}

```

## -parameters

### -param Channel

A handle for a channel.

## -returns

The value previously saved by using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbpacketsetpointer">VmbPacketSetPointer</a>.

## -remarks

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbpacketsetpointer">VmbPacketSetPointer</a>
