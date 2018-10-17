---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_DELETE_GPADL
title: FN_VMB_CHANNEL_DELETE_GPADL
author: windows-driver-content
description: The VmbChannelDeleteGpadl function deletes a Guest Physical Address Descriptor List (GPADL) mapped by the VmbChannelCreateGpadlFromMdl or VmbChannelCreateGpadlFromBuffer functions.
tech.root: netvista
ms.assetid: fa3460be-2cd1-4c04-94b7-2e83f6b243a3
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
-	FN_VMB_CHANNEL_DELETE_GPADL
product:
-	Windows
targetos: Windows
---

# FN_VMB_CHANNEL_DELETE_GPADL callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelDeleteGpadl</b> function deletes a Guest Physical Address Descriptor List (GPADL) mapped by the <a href="https://msdn.microsoft.com/6C63E250-1A11-45E8-B535-263806DA4A33">VmbChannelCreateGpadlFromMdl</a> or
<a href="https://msdn.microsoft.com/B45E2463-1EBC-4F32-B3AD-8331E664BB24">VmbChannelCreateGpadlFromBuffer</a> functions. If the GPADL is currently mapped to the server, this function is blocked until the GPADL is unmapped.

## -prototype

```
//Declaration

FN_VMB_CHANNEL_DELETE_GPADL FnVmbChannelDeleteGpadl; 

// Definition

VOID FnVmbChannelDeleteGpadl 
(
	VMBCHANNEL Channel
	UINT32 GpadlHandle
)
{...}

```

## -parameters

### -param Channel

A handle for a channel.

### -param GpadlHandle

The GPADL handle of the GPADL to delete.

## -returns

This function does not return a value.

## -remarks

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also

<a href="https://msdn.microsoft.com/B45E2463-1EBC-4F32-B3AD-8331E664BB24">VmbChannelCreateGpadlFromBuffer</a>



<a href="https://msdn.microsoft.com/6C63E250-1A11-45E8-B535-263806DA4A33">VmbChannelCreateGpadlFromMdl</a>
