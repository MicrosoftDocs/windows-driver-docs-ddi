---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_GET_INTERFACE_INSTANCE
title: FN_VMB_CHANNEL_GET_INTERFACE_INSTANCE
author: windows-driver-content
description: 
ms.assetid: 57b9057a-7cbe-4a0b-96d5-4b5177c4b5a5
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
-	FN_VMB_CHANNEL_GET_INTERFACE_INSTANCE
product: Windows
targetos: Windows
---

# FN_VMB_CHANNEL_GET_INTERFACE_INSTANCE callback function

## -description

Implemented by the client driver to ... 

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

### -param Channel: 
### -param InterfaceInstance: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also