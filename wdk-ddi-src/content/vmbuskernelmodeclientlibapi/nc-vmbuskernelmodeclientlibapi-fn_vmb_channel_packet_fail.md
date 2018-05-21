---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_PACKET_FAIL
title: FN_VMB_CHANNEL_PACKET_FAIL
author: windows-driver-content
description: 
ms.assetid: 00f1f4c0-60d4-46c9-b8c4-038e19cf5658
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
-	FN_VMB_CHANNEL_PACKET_FAIL
product: Windows
targetos: Windows
---

# FN_VMB_CHANNEL_PACKET_FAIL callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

FN_VMB_CHANNEL_PACKET_FAIL FnVmbChannelPacketFail; 

// Definition

VOID FnVmbChannelPacketFail 
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