---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_PACKET_SET_POINTER
title: FN_VMB_PACKET_SET_POINTER
author: windows-driver-content
description: 
ms.assetid: 5c6d8399-50ff-466c-9942-8b5232b841ad
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
-	FN_VMB_PACKET_SET_POINTER
product: Windows
targetos: Windows
---

# FN_VMB_PACKET_SET_POINTER callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

FN_VMB_PACKET_SET_POINTER FnVmbPacketSetPointer; 

// Definition

VOID FnVmbPacketSetPointer 
(
	VMBPACKET PacketObject
	PVOID Pointer
)
{...}

```

## -parameters

### -param PacketObject: 
### -param Pointer: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also