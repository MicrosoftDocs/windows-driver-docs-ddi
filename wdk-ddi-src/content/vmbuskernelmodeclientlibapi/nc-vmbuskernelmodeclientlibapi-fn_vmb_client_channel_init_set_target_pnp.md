---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CLIENT_CHANNEL_INIT_SET_TARGET_PNP
title: FN_VMB_CLIENT_CHANNEL_INIT_SET_TARGET_PNP
author: windows-driver-content
description: 
ms.assetid: 0c201a5e-9e06-4cab-a062-b6c9aab7ec40
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
-	FN_VMB_CLIENT_CHANNEL_INIT_SET_TARGET_PNP
product: Windows
targetos: Windows
---

# FN_VMB_CLIENT_CHANNEL_INIT_SET_TARGET_PNP callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

FN_VMB_CLIENT_CHANNEL_INIT_SET_TARGET_PNP FnVmbClientChannelInitSetTargetPnp; 

// Definition

NTSTATUS FnVmbClientChannelInitSetTargetPnp 
(
	VMBCHANNEL Channel
	LPCGUID InterfaceType
	LPCGUID InterfaceInstance
	PFN_VMB_CHANNEL_PNP_FAILURE PnpFailureCallback
)
{...}

```

## -parameters

### -param Channel: 
### -param InterfaceType: 
### -param InterfaceInstance: 
### -param PnpFailureCallback: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also