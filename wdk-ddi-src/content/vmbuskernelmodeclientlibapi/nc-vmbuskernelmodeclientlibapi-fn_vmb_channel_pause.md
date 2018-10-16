---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_PAUSE
title: FN_VMB_CHANNEL_PAUSE
author: windows-driver-content
description: The VmbChannelPause function moves a channel into the paused state, which prevents new I/O.
tech.root: netvista
ms.assetid: 9e6f55f0-c12d-430f-be21-3885ed819288
ms.author: windowsdriverdev
ms.date: 05/21/2018
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
-	FN_VMB_CHANNEL_PAUSE
product:
-	Windows
targetos: Windows
---

# FN_VMB_CHANNEL_PAUSE callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelPause</b>  function moves a channel into the paused state, which prevents new I/O.

## -prototype

```cpp
//Declaration

FN_VMB_CHANNEL_PAUSE FnVmbChannelPause; 

// Definition

VOID FnVmbChannelPause 
(
	VMBCHANNEL Channel
)
{...}

```

## -parameters

### -param Channel

A handle for the channel to pause.

## -returns

This function does not return a value.

## -remarks

This function waits until the channel is in the paused state before it returns. This ensures that all packets that are waiting for completion have completed.


 If the channel is disabled, this function sets the channel to automatically
pause when it is enabled.

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also
