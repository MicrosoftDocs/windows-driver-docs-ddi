---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_GET_INTERFACE_INSTANCE
title: FN_VMB_CHANNEL_GET_INTERFACE_INSTANCE
author: windows-driver-content
description: The VmbChannelGetInterfaceInstance function gets the active interface instance, which is a GUID that uniquely identifies a channel.
tech.root: netvista
ms.assetid: 57b9057a-7cbe-4a0b-96d5-4b5177c4b5a5
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
-	FN_VMB_CHANNEL_GET_INTERFACE_INSTANCE
product:
-	Windows
targetos: Windows
---

# FN_VMB_CHANNEL_GET_INTERFACE_INSTANCE callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelGetInterfaceInstance</b> function gets the active interface instance, which is a GUID that uniquely identifies a channel.

## -prototype

```
//Declaration

FN_VMB_CHANNEL_GET_INTERFACE_INSTANCE FnVmbChannelGetInterfaceInstance; 

// Definition

VOID FnVmbChannelGetInterfaceInstance 
(
	VMBCHANNEL Channel
	LPGUID InterfaceInstance
)
{...}

```

## -parameters

### -param Channel

The channel for which to get an instance.

### -param InterfaceInstance

A pointer to a GUID, which is the interface instance
of the channel.

## -returns

This function does not return a value.

## -remarks

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also
