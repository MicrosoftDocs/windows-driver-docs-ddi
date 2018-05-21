---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_PACKET_COMPLETE
title: FN_VMB_CHANNEL_PACKET_COMPLETE
author: windows-driver-content
description: 
ms.assetid: 371b8ad4-4777-427c-9b9f-6c9c07bb9c3d
ms.author: windowsdriverdev
ms.date: 
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
-	FN_VMB_CHANNEL_PACKET_COMPLETE
product: Windows
targetos: Windows
---

# FN_VMB_CHANNEL_PACKET_COMPLETE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

FN_VMB_CHANNEL_PACKET_COMPLETE FnVmbChannelPacketComplete; 

// Definition

VOID FnVmbChannelPacketComplete 
(
	VMBPACKETCOMPLETION PacketCompletionContext
	PVOID PacketCompletionBuffer
	UINT32 BufSize
)
{...}

```

## -parameters

### -param PacketCompletionContext: 
### -param PacketCompletionBuffer: 
### -param BufSize: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also