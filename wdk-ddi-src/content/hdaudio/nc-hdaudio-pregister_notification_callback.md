---
UID: NC:hdaudio.PREGISTER_NOTIFICATION_CALLBACK
title: PREGISTER_NOTIFICATION_CALLBACK
author: windows-driver-content
description: The RegisterNotificationCallback routine registers a callback routine so that it can receive DMA progress notifications with more accurate timing information.
tech.root: audio
ms.assetid: 453c5313-24a0-4009-98bd-9bba2a546a75
ms.author: windowsdriverdev
ms.date: 04/29/2019 
ms.topic: callback
f1_keywords:
 - "hdaudio/PREGISTER_NOTIFICATION_CALLBACK"
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
req.irql: PASSIVE_LEVEL
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
- PREGISTER_NOTIFICATION_CALLBACK
product: 
- Windows
targetos: Windows
ms.custom: 19H1 
---

# PREGISTER_NOTIFICATION_CALLBACK callback function

## -description

The RegisterNotificationCallback routine registers a callback routine so that it can receive DMA progress notifications with more accurate timing information.


## -prototype

The function pointer type for a RegisterNotificationCallback routine is defined as follows.

```
//Declaration

PREGISTER_NOTIFICATION_CALLBACK PRegisterNotificationCallback; 

// Definition

NTSTATUS PRegisterNotificationCallback 
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

### -param _context 
Specifies the context value from the Context member of the [HDAUDIO_BUS_INTERFACE_V3](ns-hdaudio-_hdaudio_bus_interface_v3.md) structure.

### -param Handle 
Handle that identifies the DMA engine. This handle value was obtained from a previous call to AllocateCaptureDmaEngine or AllocateRenderDmaEngine.

### -param Fdo 
The FDO that owns the callback. The hdaudbus driver will take a reference on this FDO while the callback is registered to ensure the callback routine is valid.

### -param NotificationCallback 
The callback routine that will be called to notify the driver as DMA is progressing. Depending on the notification count parameter that is used with AllocateDmaBufferWithNotification, the registered event is signaled one or two times for every time that the DMA passes through the audio buffer.

### -param CallbackContext 
Driver-specific context value for the callback routine.

## -returns

RegisterNotificationCallback returns STATUS_SUCCESS if the call successfully registers the event. Otherwise, the routine returns STATUS_INSUFFICIENT_RESOURCES to indicate that there are insufficient resources that are available to complete the operation. 

For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

RegisterNotificationCallback registers the notification callback routine with the HD Audio bus driver. The HD Audio bus driver maintains a list of the registered notification events and callback routines for each DMA engine. Every time the engine receives an IOC interrupt all events will be signaled and all notification callback routines will be called at IRQL=DPC with the QPC timestamp at the time the IOC occurred.

Notification Callback routines are unregistered by calling UnregisterNotificationCallback with the same NotificationCallback and CallbackContext values.

The HD Audio bus driver will maintain a reference on the FDO after registration until the matching unregistration is called.


## -see-also

[HDAUDIO_BUS_INTERFACE_V3](ns-hdaudio-_hdaudio_bus_interface_v3.md)

[PREGISTER_NOTIFICATION_CALLBACK callback function](nc-hdaudio-pregister_notification_callback.md)

[hdaudio.h](../hdaudio/index.md)
