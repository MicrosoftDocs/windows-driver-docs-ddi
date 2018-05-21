---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_SEND_SYNCHRONOUS_REQUEST
title: FN_VMB_CHANNEL_SEND_SYNCHRONOUS_REQUEST
author: windows-driver-content
description: 
ms.assetid: 353b996b-0678-4ce6-aaeb-3835ae05ee3e
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
-	FN_VMB_CHANNEL_SEND_SYNCHRONOUS_REQUEST
product: Windows
targetos: Windows
---

# FN_VMB_CHANNEL_SEND_SYNCHRONOUS_REQUEST callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

FN_VMB_CHANNEL_SEND_SYNCHRONOUS_REQUEST FnVmbChannelSendSynchronousRequest; 

// Definition

NTSTATUS FnVmbChannelSendSynchronousRequest 
(
	VMBCHANNEL Channel
	PVOID Buffer
	UINT32 BufferSize
	PMDL ExternalDataMdl
	UINT32 Flags
	PVOID CompletionBuffer
	PUINT32 CompletionBufferSize
	PLARGE_INTEGER Timeout
)
{...}

```

## -parameters

### -param Channel: 
### -param Buffer: 
### -param BufferSize: 
### -param ExternalDataMdl: 
### -param Flags: 
### -param CompletionBuffer: 
### -param CompletionBufferSize: 
### -param Timeout: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also