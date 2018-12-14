---
UID: NC:hdaudio.PREGISTER_NOTIFICATION_CALLBACK
title: PREGISTER_NOTIFICATION_CALLBACK
author: windows-driver-content
description: 
ms.assetid: 453c5313-24a0-4009-98bd-9bba2a546a75
ms.author: windowsdriverdev
ms.date: 12/13/2018 
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
-	apiref
api_type: 
-	UserDefined
api_location: 
-	hdaudio.h
api_name: 
-	PREGISTER_NOTIFICATION_CALLBACK
product: Windows
targetos: Windows
---

# PREGISTER_NOTIFICATION_CALLBACK callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PREGISTER_NOTIFICATION_CALLBACK PregisterNotificationCallback; 

// Definition

NTSTATUS PregisterNotificationCallback 
(
	PVOID _context
	HANDLE Handle
	PDEVICE_OBJECT Fdo
	PHDAUDIO_DMA_NOTIFICATION_CALLBACK NotificationCallback
	PVOID CallbackContext
)
{...}

```

## -parameters

### -param _context: 
### -param Handle: 
### -param Fdo: 
### -param NotificationCallback: 
### -param CallbackContext: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also