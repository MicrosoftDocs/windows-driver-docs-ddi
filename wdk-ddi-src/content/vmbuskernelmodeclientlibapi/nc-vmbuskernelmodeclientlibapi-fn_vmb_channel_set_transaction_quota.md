---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_SET_TRANSACTION_QUOTA
title: FN_VMB_CHANNEL_SET_TRANSACTION_QUOTA
author: windows-driver-content
description: 
ms.assetid: a5e56060-b5b9-4d65-8808-1d4a430521fa
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
-	FN_VMB_CHANNEL_SET_TRANSACTION_QUOTA
product: Windows
targetos: Windows
---

# FN_VMB_CHANNEL_SET_TRANSACTION_QUOTA callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

FN_VMB_CHANNEL_SET_TRANSACTION_QUOTA FnVmbChannelSetTransactionQuota; 

// Definition

VOID FnVmbChannelSetTransactionQuota 
(
	VMBCHANNEL Channel
	UINT32 Quota
)
{...}

```

## -parameters

### -param Channel: 
### -param Quota: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also