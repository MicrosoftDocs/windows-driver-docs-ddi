---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_INIT_SET_PROCESS_PACKET_CALLBACKS
title: FN_VMB_CHANNEL_INIT_SET_PROCESS_PACKET_CALLBACKS
author: windows-driver-content
description: 
ms.assetid: 863dc828-cd80-480a-99ee-0314824e4b8b
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
-	FN_VMB_CHANNEL_INIT_SET_PROCESS_PACKET_CALLBACKS
product: Windows
targetos: Windows
---

# FN_VMB_CHANNEL_INIT_SET_PROCESS_PACKET_CALLBACKS callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

FN_VMB_CHANNEL_INIT_SET_PROCESS_PACKET_CALLBACKS FnVmbChannelInitSetProcessPacketCallbacks; 

// Definition

NTSTATUS FnVmbChannelInitSetProcessPacketCallbacks 
(
	VMBCHANNEL Channel
	PFN_VMB_CHANNEL_PROCESS_PACKET ProcessPacketCallback
	PFN_VMB_CHANNEL_PROCESSING_COMPLETE ProcessingCompleteCallback
)
{...}

```

## -parameters

### -param Channel: 
### -param ProcessPacketCallback: 
### -param ProcessingCompleteCallback: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also