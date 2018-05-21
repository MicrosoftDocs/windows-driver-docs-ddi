---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_GET_MMIO_SPACE
title: FN_VMB_CHANNEL_GET_MMIO_SPACE
author: windows-driver-content
description: 
ms.assetid: c34ca88d-10bb-49c5-bddc-606367926b0c
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
-	FN_VMB_CHANNEL_GET_MMIO_SPACE
product: Windows
targetos: Windows
---

# FN_VMB_CHANNEL_GET_MMIO_SPACE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

FN_VMB_CHANNEL_GET_MMIO_SPACE FnVmbChannelGetMmioSpace; 

// Definition

VOID FnVmbChannelGetMmioSpace 
(
	VMBCHANNEL Channel
	UINT64 *MmioAddress
	UINT64 *MmioSize
)
{...}

```

## -parameters

### -param Channel: 
### -param *MmioAddress: 
### -param *MmioSize: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also