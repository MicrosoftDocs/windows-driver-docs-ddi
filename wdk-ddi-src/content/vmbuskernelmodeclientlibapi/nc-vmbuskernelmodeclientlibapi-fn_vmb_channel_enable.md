---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_ENABLE
title: FN_VMB_CHANNEL_ENABLE
author: windows-driver-content
description: 
ms.assetid: e2761a5b-dac3-4423-93af-5f009c2cfaad
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
-	FN_VMB_CHANNEL_ENABLE
product: Windows
targetos: Windows
---

# FN_VMB_CHANNEL_ENABLE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

FN_VMB_CHANNEL_ENABLE FnVmbChannelEnable; 

// Definition

NTSTATUS FnVmbChannelEnable 
(
	VMBCHANNEL Channel
)
{...}

```

## -parameters

### -param Channel: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also