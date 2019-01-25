---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_INIT_SET_FRIENDLY_NAME
title: FN_VMB_CHANNEL_INIT_SET_FRIENDLY_NAME (vmbuskernelmodeclientlibapi.h)
description:  The VmbChannelInitSetFriendlyName function sets the friendly name of the Kernel Mode Client Library (KMCL) channel. The friendly name is used for debugging and performance counter instance naming.
tech.root: netvista
ms.assetid: a5ee22a8-d216-48ba-925a-498b912ddc67
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
-	FN_VMB_CHANNEL_INIT_SET_FRIENDLY_NAME
product:
-	Windows
targetos: Windows
ms.custom: RS5
---

# FN_VMB_CHANNEL_INIT_SET_FRIENDLY_NAME callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelInitSetFriendlyName</b> function sets the friendly name of the Kernel Mode Client Library (KMCL) channel.  The friendly name is used for debugging and
performance counter instance naming. 

## -prototype

```cpp
//Declaration

FN_VMB_CHANNEL_INIT_SET_FRIENDLY_NAME FnVmbChannelInitSetFriendlyName; 

// Definition

NTSTATUS FnVmbChannelInitSetFriendlyName 
(
	VMBCHANNEL Channel
	PCUNICODE_STRING Name
)
{...}

```

## -parameters

### -param Channel

A handle for the channel to name.

### -param Name: 

The new friendly name of the channel.

## -returns

Returns STATUS_SUCCESS if the operation succeeds, or an appropriate NTSTATUS error code otherwise.

## -remarks

Channel names should be descriptive, yet
relatively short and easy to understand, for example, Network, SCSI, IDE, or SynthVideo.

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also
