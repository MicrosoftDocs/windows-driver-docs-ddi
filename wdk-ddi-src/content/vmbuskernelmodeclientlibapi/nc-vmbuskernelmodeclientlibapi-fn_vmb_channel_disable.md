---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_DISABLE
title: FN_VMB_CHANNEL_DISABLE (vmbuskernelmodeclientlibapi.h)
description: The VmbChannelDisable function disables a channel, which closes it for client channels and revokes the channel offer for server channels. This function waits until the channel is completely torn down before it returns.
tech.root: netvista
ms.date: 05/21/2018
keywords: ["FN_VMB_CHANNEL_DISABLE callback function"]
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
 - FN_VMB_CHANNEL_DISABLE
 - vmbuskernelmodeclientlibapi/FN_VMB_CHANNEL_DISABLE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - vmbuskernelmodeclientlibapi.h
api_name:
 - FN_VMB_CHANNEL_DISABLE
---

# FN_VMB_CHANNEL_DISABLE callback function


## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelDisable</b> function disables a channel, which closes it for client channels and revokes the channel offer for server channels. This function waits until the channel is completely torn down
before it returns.

## -parameters

### -param Channel

The handle of a channel to disable.

## -prototype

```cpp
//Declaration

FN_VMB_CHANNEL_DISABLE FnVmbChannelDisable; 

// Definition

VOID FnVmbChannelDisable 
(
	VMBCHANNEL Channel
)
{...}

```

## -remarks

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also

