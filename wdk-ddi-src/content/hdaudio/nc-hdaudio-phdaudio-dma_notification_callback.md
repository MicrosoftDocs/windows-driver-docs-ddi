---
UID: NC:hdaudio.PHDAUDIO_DMA_NOTIFICATION_CALLBACK
title: PHDAUDIO_DMA_NOTIFICATION_CALLBACK
description: HDAudio codec DMA Notification Callback function.
tech.root: audio
ms.date: 04/08/2019
keywords: ["PHDAUDIO_DMA_NOTIFICATION_CALLBACK callback function"]
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
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - PHDAUDIO_DMA_NOTIFICATION_CALLBACK
 - hdaudio/PHDAUDIO_DMA_NOTIFICATION_CALLBACK
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
---

# PHDAUDIO_DMA_NOTIFICATION_CALLBACK callback function


## -description

HDAudio codec DMA Notification Callback function. 

**PHDAUDIO_DMA_NOTIFICATION_CALLBACK** is used by the [PREGISTER_NOTIFICATION_CALLBACK](nc-hdaudio-pregister_notification_callback.md) callback function.

## -parameters

### -param Context:

Driver-specific context value used when registering the callback routine.

### -param QPCDMANotificationTimestamp:

The QPC time when the IOC ISR handled the DMA interrupt.

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

## -remarks

## -see-also

[hdaudio.h](../hdaudio/index.md)

