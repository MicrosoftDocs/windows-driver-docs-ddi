---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_PACKET_SET_COMPLETION_ROUTINE
title: FN_VMB_PACKET_SET_COMPLETION_ROUTINE
author: windows-driver-content
description: The VmbPacketSetCompletionRoutine function sets the completion routine for a packet object.
tech.root: netvista
ms.assetid: e59dd45b-4158-4f05-a513-e1e97e82228c
ms.author: windowsdriverdev
ms.date: 05/22/2018
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
-	FN_VMB_PACKET_SET_COMPLETION_ROUTINE
product:
-	Windows
targetos: Windows
---

# FN_VMB_PACKET_SET_COMPLETION_ROUTINE callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbPacketSetCompletionRoutine</b> function sets the completion routine for a packet object. 

## -prototype

```cpp
//Declaration

FN_VMB_PACKET_SET_COMPLETION_ROUTINE FnVmbPacketSetCompletionRoutine; 

// Definition

VOID FnVmbPacketSetCompletionRoutine 
(
	VMBPACKET PacketObject
	PFN_VMB_PACKET_COMPLETION_ROUTINE CompletionRoutine
)
{...}

```

## -parameters

### -param PacketObject

The packet for which to specify a completion routine.

### -param CompletionRoutine

Function to call when the packet is completed.

## -returns

This function does not return a value.

## -remarks

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also

<a href="https://msdn.microsoft.com/DEE6FBD6-4807-4216-9010-F59C9E08076B">EvtVmbPacketCompletionRoutine</a>



<a href="https://msdn.microsoft.com/EBB981CB-0107-497A-B6E6-9271E22A8D5F">VmbPacketSend</a>



<a href="https://msdn.microsoft.com/C1B3FA0C-65B8-4CE1-B8F5-650DF54C9E1E">VmbPacketSendWithExternalMdl</a>



<a href="https://msdn.microsoft.com/50AACCAB-EFEA-42B7-8A34-FE110C7CDEED">VmbPacketSendWithExternalPfns</a>
