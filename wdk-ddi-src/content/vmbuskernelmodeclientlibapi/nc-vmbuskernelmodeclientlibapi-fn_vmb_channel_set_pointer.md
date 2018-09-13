---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_SET_POINTER
title: FN_VMB_CHANNEL_SET_POINTER
author: windows-driver-content
description: The VmbChannelSetPointer function saves an arbitrary pointer in a channel context.
ms.assetid: aa582790-1277-4516-89fb-bff16ed3b8e7
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
-	FN_VMB_CHANNEL_SET_POINTER
product:
-	Windows
targetos: Windows
---

# FN_VMB_CHANNEL_SET_POINTER callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelSetPointer</b> function saves an arbitrary pointer in a channel
context. 

## -prototype

```
//Declaration

FN_VMB_CHANNEL_SET_POINTER FnVmbChannelSetPointer; 

// Definition

VOID FnVmbChannelSetPointer 
(
	VMBCHANNEL Channel
	__drv_aliasesMem PVOID Pointer
)
{...}

```

## -parameters

### -param Channel

A handle for a channel. 

### -param Pointer

Arbitrary pointer to save in the channel's context.

## -returns

This function does not return a value.

## -remarks

  This is intended to be a more efficient way for a client driver to retrieve client driver's context.  For more information, see the <a href="https://msdn.microsoft.com/F3BEE6FB-51C5-4C3C-A831-3B7C06B3C14D">VmbChannelGetPointer</a> function.

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also

<a href="https://msdn.microsoft.com/F3BEE6FB-51C5-4C3C-A831-3B7C06B3C14D">VmbChannelGetPointer</a>