---
UID: NC:hdaudio.PHDAUDIO_DMA_NOTIFICATION_CALLBACK
title: PHDAUDIO_DMA_NOTIFICATION_CALLBACK
author: windows-driver-content
description: 
tech.root: audio
ms.assetid: 5f618d11-1d66-4bf8-8176-91101c5355f3
ms.author: windowsdriverdev
ms.date: 12/18/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: hdaudio.h
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
 - apiref
api_type: 
 - UserDefined
api_location: 
 - hdaudio.h
api_name: 
 - PHDAUDIO_DMA_NOTIFICATION_CALLBACK
product: 
 - Windows
targetos: Windows
---

# PHDAUDIO_DMA_NOTIFICATION_CALLBACK callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PHDAUDIO_DMA_NOTIFICATION_CALLBACK PhdaudioDmaNotificationCallback; 

// Definition

VOID PhdaudioDmaNotificationCallback 
(
	PVOID Arg1
	LARGE_INTEGER Arg2
)
{...}

```

## -parameters

### -param Arg1: 
### -param Arg2: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also