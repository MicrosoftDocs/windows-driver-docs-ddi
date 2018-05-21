---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_SET_INCOMING_PROCESSING_AT_PASSIVE
title: FN_VMB_CHANNEL_SET_INCOMING_PROCESSING_AT_PASSIVE
author: windows-driver-content
description: 
ms.assetid: 8bdd8690-6c8e-4764-91da-5a35922dae65
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
-	FN_VMB_CHANNEL_SET_INCOMING_PROCESSING_AT_PASSIVE
product: Windows
targetos: Windows
---

# FN_VMB_CHANNEL_SET_INCOMING_PROCESSING_AT_PASSIVE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
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

### -param Channel: 
### -param RequirePassive: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also