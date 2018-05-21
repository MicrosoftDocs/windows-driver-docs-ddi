---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_GET_POINTER
title: FN_VMB_CHANNEL_GET_POINTER
author: windows-driver-content
description: 
ms.assetid: 58de32e6-224f-4c54-b07e-9a8494d7ac63
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
-	FN_VMB_CHANNEL_GET_POINTER
product: Windows
targetos: Windows
---

# FN_VMB_CHANNEL_GET_POINTER callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

FN_VMB_CHANNEL_GET_POINTER FnVmbChannelGetPointer; 

// Definition

PVOID FnVmbChannelGetPointer 
(
	VMBCHANNEL Channel
)
{...}

```

## -parameters

### -param Channel: 



## -returns

Returns PVOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also