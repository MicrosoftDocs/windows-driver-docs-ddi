---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_SET_INCOMING_PROCESSING_AT_PASSIVE
title: FN_VMB_CHANNEL_SET_INCOMING_PROCESSING_AT_PASSIVE
description: The VmbChannelSetIncomingProcessingAtPassive function sets the required IRQL for incoming parsing routines for a channel to PASSIVE_LEVEL.
tech.root: netvista
ms.assetid: 8bdd8690-6c8e-4764-91da-5a35922dae65
ms.date: 05/22/2018
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
-	FN_VMB_CHANNEL_SET_INCOMING_PROCESSING_AT_PASSIVE
product:
-	Windows
targetos: Windows
ms.custom: RS5
---

# FN_VMB_CHANNEL_SET_INCOMING_PROCESSING_AT_PASSIVE callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelSetIncomingProcessingAtPassive</b> function sets the required IRQL for incoming parsing routines for a channel to
PASSIVE_LEVEL.

## -prototype

```cpp
//Declaration

FN_VMB_CHANNEL_SET_INCOMING_PROCESSING_AT_PASSIVE FnVmbChannelSetIncomingProcessingAtPassive; 

// Definition

VOID FnVmbChannelSetIncomingProcessingAtPassive 
(
	VMBCHANNEL Channel
	BOOLEAN RequirePassive
)
{...}

```

## -parameters

### -param Channel

A handle for a channel. 

### -param RequirePassive

If true, the channel requires PASSIVE_LEVEL. If false, packets may arrive at either DISPATCH_LEVEL or PASSIVE_LEVEL.

## -returns

This function does not return a value.

## -remarks

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also
