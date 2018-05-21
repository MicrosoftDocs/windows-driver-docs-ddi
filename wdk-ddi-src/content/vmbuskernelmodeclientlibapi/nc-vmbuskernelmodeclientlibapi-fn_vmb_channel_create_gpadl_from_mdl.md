---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_CREATE_GPADL_FROM_MDL
title: FN_VMB_CHANNEL_CREATE_GPADL_FROM_MDL
author: windows-driver-content
description: 
ms.assetid: 910ee2ef-69af-448c-b911-b9cfe782eb74
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
-	FN_VMB_CHANNEL_CREATE_GPADL_FROM_MDL
product: Windows
targetos: Windows
---

# FN_VMB_CHANNEL_CREATE_GPADL_FROM_MDL callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

FN_VMB_CHANNEL_CREATE_GPADL_FROM_MDL FnVmbChannelCreateGpadlFromMdl; 

// Definition

NTSTATUS FnVmbChannelCreateGpadlFromMdl 
(
	VMBCHANNEL Channel
	UINT32 Flags
	PMDL Mdl
	UINT32 StartOffsetWithinMdl
	UINT32 DataLengthWithinMdl
	PUINT32 GpadlHandle
)
{...}

```

## -parameters

### -param Channel: 
### -param Flags: 
### -param Mdl: 
### -param StartOffsetWithinMdl: 
### -param DataLengthWithinMdl: 
### -param GpadlHandle: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also