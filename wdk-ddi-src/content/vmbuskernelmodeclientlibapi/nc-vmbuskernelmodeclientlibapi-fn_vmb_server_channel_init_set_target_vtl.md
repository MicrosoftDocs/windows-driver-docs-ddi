---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_SERVER_CHANNEL_INIT_SET_TARGET_VTL
title: FN_VMB_SERVER_CHANNEL_INIT_SET_TARGET_VTL
author: windows-driver-content
description: The VmbServerChannelInitSetTargetVtl function sets the target VTL for this channel. The channel will be offered to clients running in the specified VTL and no others.
ms.assetid: dde46e18-27a0-4d4d-85bc-1bd05d61d5a1
ms.author: windowsdriverdev
ms.date: 09/13/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: vmbuskernelmodeclientlibapi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
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
-	FN_VMB_SERVER_CHANNEL_INIT_SET_TARGET_VTL
product: 
- Windows
targetos: Windows
tech.root: netvista
---

# FN_VMB_SERVER_CHANNEL_INIT_SET_TARGET_VTL callback function

## -description

The **VmbServerChannelInitSetTargetVtl** function sets the target VTL for this channel. The channel will be offered to clients running in the specified VTL and no others.

## -prototype

```
//Declaration

FN_VMB_SERVER_CHANNEL_INIT_SET_TARGET_VTL FnVmbServerChannelInitSetTargetVtl; 

// Definition

NTSTATUS FnVmbServerChannelInitSetTargetVtl 
(
	VMBCHANNEL Channel
	UINT8 TargetVtl
)
{...}

```

## -parameters

### -param Channel

A handle for the channel. Allocated by [**VmbChannelAllocate**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_allocate.md).

### -param TargetVtl

The VTL level where this channel will be offered.

## -returns

**VmbServerChannelInitSetTargetVtl** returns the following status values:

| Return code | Description |
| --- | --- |
| STATUS_INVALID_PARAMETER_1 | The **Channel** parameter was invalid or in an invalid state (Disabled).
| STATUS_INVALID_PARAMETER_2 | **TargetVtl** is invalid. |

## -remarks

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a server-only function accessed from the [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md) structure. 
>
> For more information, see the Remarks section of [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md).

## -see-also

[**VmbChannelAllocate**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_allocate.md)
