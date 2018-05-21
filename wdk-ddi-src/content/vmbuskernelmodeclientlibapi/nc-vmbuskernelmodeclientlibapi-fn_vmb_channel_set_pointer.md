---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_SET_POINTER
title: FN_VMB_CHANNEL_SET_POINTER
author: windows-driver-content
description: 
ms.assetid: aa582790-1277-4516-89fb-bff16ed3b8e7
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
-	FN_VMB_CHANNEL_SET_POINTER
product: Windows
targetos: Windows
---

# FN_VMB_CHANNEL_SET_POINTER callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

FN_VMB_CHANNEL_SET_POINTER FnVmbChannelSetPointer; 

// Definition

VOID FnVmbChannelSetPointer 
(
	VMBCHANNEL Channel
	__drv_aliasesMem PVOID Pointer
)
{...}

```

## -parameters

### -param Channel: 
### -param Pointer: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also