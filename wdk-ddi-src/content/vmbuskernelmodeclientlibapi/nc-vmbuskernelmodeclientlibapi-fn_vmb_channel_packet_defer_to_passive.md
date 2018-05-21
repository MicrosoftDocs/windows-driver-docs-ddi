---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_PACKET_DEFER_TO_PASSIVE
title: FN_VMB_CHANNEL_PACKET_DEFER_TO_PASSIVE
author: windows-driver-content
description: 
ms.assetid: 7226008d-7c72-4f80-a100-3441c199ba48
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
-	FN_VMB_CHANNEL_PACKET_DEFER_TO_PASSIVE
product: Windows
targetos: Windows
---

# FN_VMB_CHANNEL_PACKET_DEFER_TO_PASSIVE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

FN_VMB_CHANNEL_PACKET_DEFER_TO_PASSIVE FnVmbChannelPacketDeferToPassive; 

// Definition

VOID FnVmbChannelPacketDeferToPassive 
(
	VMBPACKETCOMPLETION PacketCompletionContext
)
{...}

```

## -parameters

### -param PacketCompletionContext: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also