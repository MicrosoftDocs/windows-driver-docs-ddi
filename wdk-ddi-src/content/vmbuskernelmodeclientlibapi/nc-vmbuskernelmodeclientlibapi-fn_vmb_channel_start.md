---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_START
title: FN_VMB_CHANNEL_START
author: windows-driver-content
description: The VmbChannelStart function moves a channel out of the paused state.
ms.assetid: 2cc86b88-53af-4207-9bd2-829c950f87d8
ms.author: windowsdriverdev
ms.date: 05/22/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: vmbuskernelmodeclientlibapi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
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
-	FN_VMB_CHANNEL_START
product:
-	Windows
targetos: Windows
---

# FN_VMB_CHANNEL_START callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelStart</b> function moves a channel out of the paused state.

## -prototype

```
//Declaration

FN_VMB_CHANNEL_START FnVmbChannelStart; 

// Definition

VOID FnVmbChannelStart 
(
	VMBCHANNEL Channel
)
{...}

```

## -parameters

### -param Channel

A handle for a channel that this function modifies.

## -returns

This function does not return a value.

## -remarks

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also