---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_SAVE_END
title: FN_VMB_CHANNEL_SAVE_END (vmbuskernelmodeclientlibapi.h)
description: The VmbChannelSaveEnd function cleans up any resources that were allocated for saving state of a channel.
tech.root: netvista
ms.assetid: 9de0f0e0-edee-4f91-be92-a4d7a439ec5a
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
- apiref
api_type: 
- UserDefined
api_location: 
- vmbuskernelmodeclientlibapi.h
api_name: 
- FN_VMB_CHANNEL_SAVE_END
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# FN_VMB_CHANNEL_SAVE_END callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelSaveEnd</b> function cleans up any resources that were allocated for saving state of a channel.

## -prototype

```cpp
//Declaration

FN_VMB_CHANNEL_SAVE_END FnVmbChannelSaveEnd; 

// Definition

VOID FnVmbChannelSaveEnd 
(
	VMBCHANNEL Channel
)
{...}

```

## -parameters

### -param Channel

A handle of the channel that was saved. 

## -returns

This function does not return a value.

## -remarks

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a server-only function accessed from the [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md) structure. 
>
> For more information, see the Remarks section of [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md).

## -see-also

[**VmbChannelSaveBegin**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_save_begin.md)

[**VmbChannelSaveContinue**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_save_continue.md)
