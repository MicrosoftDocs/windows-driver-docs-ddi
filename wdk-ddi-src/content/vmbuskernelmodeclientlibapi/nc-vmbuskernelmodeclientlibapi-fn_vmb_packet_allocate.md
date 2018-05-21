---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_PACKET_ALLOCATE
title: FN_VMB_PACKET_ALLOCATE
author: windows-driver-content
description: 
ms.assetid: de59b2ba-33eb-41f2-a4ce-6be46e88dfd7
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
-	FN_VMB_PACKET_ALLOCATE
product: Windows
targetos: Windows
---

# FN_VMB_PACKET_ALLOCATE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

FN_VMB_PACKET_ALLOCATE FnVmbPacketAllocate; 

// Definition

VMBPACKET FnVmbPacketAllocate 
(
	VMBCHANNEL Channel
)
{...}

```

## -parameters

### -param Channel: 



## -returns

Returns VMBPACKET that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also