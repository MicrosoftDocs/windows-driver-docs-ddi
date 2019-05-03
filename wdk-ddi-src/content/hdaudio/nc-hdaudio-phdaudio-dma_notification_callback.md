---
UID: NC:hdaudio.PHDAUDIO_DMA_NOTIFICATION_CALLBACK
title: PHDAUDIO_DMA_NOTIFICATION_CALLBACK
author: windows-driver-content
description: HDAudio codec DMA Notification Callback function. 
tech.root: audio
ms.assetid: 5f618d11-1d66-4bf8-8176-91101c5355f3
ms.author: windowsdriverdev
ms.date: 04/08/2019
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: hdaudio.h
req.include-header: hdaudio.h
req.target-type:
req.target-min-winverclnt: 19H1
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: DPC_LEVEL
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
ms.custom: 19H1
---

# PHDAUDIO_DMA_NOTIFICATION_CALLBACK callback function

## -description

HDAudio codec DMA Notification Callback function. 

**PHDAUDIO_DMA_NOTIFICATION_CALLBACK** is used by the [PREGISTER_NOTIFICATION_CALLBACK](nc-hdaudio-pregister_notification_callback.md) callback function.

## -prototype

```
//Declaration

PHDAUDIO_DMA_NOTIFICATION_CALLBACK PHdAudioDmaNotificationCallback; 

// Definition

VOID PHdAudioDmaNotificationCallback 
(
	PVOID Context
	LARGE_INTEGER QPCDMANotificationTimestamp 
)
{...}

```

## -parameters

### -param Context:

Driver-specific context value used when registering the callback routine.


### -param QPCDMANotificationTimestamp:

The QPC time when the IOC ISR handled the DMA interrupt. 


## -returns

Returns VOID.


## -remarks



## -see-also

[hdaudio.h](../hdaudio/index.md)