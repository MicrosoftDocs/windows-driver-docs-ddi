---
UID: NC:hdaudio.PUNREGISTER_NOTIFICATION_CALLBACK
title: PUNREGISTER_NOTIFICATION_CALLBACK
description: The PUNREGISTER_NOTIFICATION_CALLBACK callback function deletes the registration of a notification callback routine that was previously registered by a call to RegisterNotificationCallback.
tech.root: audio
ms.assetid: 453c5313-24a0-4009-98bd-9bba2a546a75
ms.author: windowsdriverdev
ms.date: 04/08/2019
keywords: ["PUNREGISTER_NOTIFICATION_CALLBACK callback function"]
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: hdaudio.h
req.include-header: 
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
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - PUNREGISTER_NOTIFICATION_CALLBACK
 - hdaudio/PUNREGISTER_NOTIFICATION_CALLBACK
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - hdaudio.h
api_name:
 - PUNREGISTER_NOTIFICATION_CALLBACK
product:
 - Windows
---

# PUNREGISTER_NOTIFICATION_CALLBACK callback function


## -description

The **PUNREGISTER_NOTIFICATION_CALLBACK** callback function deletes the registration of a notification callback routine that was previously registered by a call to RegisterNotificationCallback.

## -parameters

### -param _context: 

Specifies the context value from the Context member of the [HDAUDIO_BUS_INTERFACE_V3](ns-hdaudio-_hdaudio_bus_interface_v3.md) structure.

### -param Handle: 

Handle that identifies the DMA engine. This handle value was obtained from a previous call to [AllocateCaptureDmaEngine](nc-hdaudio-pallocate_capture_dma_engine.md) or [AllocateRenderDmaEngine](nc-hdaudio-pallocate_render_dma_engine.md).

### -param NotificationCallback: 

A callback routine that was previously registered for DMA progress notification with a call to [PREGISTER_NOTIFICATION_CALLBACK](nc-hdaudio-pregister_notification_callback.md).

### -param CallbackContext: 

Driver-specific context value for the callback routine.

## -returns

PUNREGISTER_NOTIFICATION_CALLBACK returns STATUS_SUCCESS if the call successfully unregisters the notification event. Otherwise, the routine returns STATUS_INVALID_PARAMETER to indicate that the specified callback routine and context are not valid.

For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -prototype

The function pointer type for an UnregisterNotificationCallback routine is defined as follows.

```
//Declaration

PUNREGISTER_NOTIFICATION_CALLBACK PUnregisterNotificationCallback;

// Definition

NTSTATUS PUnregisterNotificationCallback(
  PVOID _context,
  HANDLE Handle,
  PHDAUDIO_DMA_NOTIFICATION_CALLBACK NotificationCallback,
  PVOID CallbackContext
)
{...}

```

## -remarks

PUNREGISTER_NOTIFICATION_CALLBACK will use both the NotificationCallback and CallbackContext to find the matching previously-registered callback routine to remove.

The HD Audio bus driver will release the reference it took on the driver FDO when the notification callback routine was previously registered.

## -see-also

[PREGISTER_NOTIFICATION_CALLBACK](nc-hdaudio-pregister_notification_callback.md)

[HDAUDIO_BUS_INTERFACE_V3](ns-hdaudio-_hdaudio_bus_interface_v3.md)

[hdaudio.h](../hdaudio/index.md)

