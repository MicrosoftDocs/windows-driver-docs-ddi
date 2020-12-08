---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_UNMAP_GPADL
title: FN_VMB_CHANNEL_UNMAP_GPADL (vmbuskernelmodeclientlibapi.h)
description: The VmbChannelUnmapGpadl function unmaps a Guest Physical Address Descriptor List (GPADL) mapped using by the VmbChannelMapGpadl function. The buffer must no longer be in use by the server before this function is called.
tech.root: netvista
ms.date: 05/22/2018
keywords: ["FN_VMB_CHANNEL_UNMAP_GPADL callback function"]
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
 - FN_VMB_CHANNEL_UNMAP_GPADL
 - vmbuskernelmodeclientlibapi/FN_VMB_CHANNEL_UNMAP_GPADL
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - vmbuskernelmodeclientlibapi.h
api_name:
 - FN_VMB_CHANNEL_UNMAP_GPADL
---

# FN_VMB_CHANNEL_UNMAP_GPADL callback function


## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelUnmapGpadl</b> function unmaps a Guest Physical Address Descriptor List (GPADL) mapped using by the <a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelmapgpadl">VmbChannelMapGpadl</a> function. The buffer must no longer be in
use by the server before this function is called.

## -parameters

### -param Channel

A handle for a channel.

### -param GpadlHandle 

The handle of the GPADL to unmap.

## -prototype

```cpp
//Declaration

FN_VMB_CHANNEL_UNMAP_GPADL FnVmbChannelUnmapGpadl; 

// Definition

VOID FnVmbChannelUnmapGpadl 
(
	VMBCHANNEL Channel
	UINT32 GpadlHandle
)
{...}

```

## -remarks

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a server-only function accessed from the [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md) structure. 
>
> For more information, see the Remarks section of [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md).

## -see-also

<a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelmapgpadl">VmbChannelMapGpadl</a>
