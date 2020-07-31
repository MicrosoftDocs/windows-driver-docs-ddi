---
UID: NC:hdaudio.PUNREGISTER_NOTIFICATION_EVENT
title: PUNREGISTER_NOTIFICATION_EVENT (hdaudio.h)
description: The UnregisterNotificationEvent routine deletes the registration of an event that was previously registered by a call to RegisterNotificationEvent.The function pointer type for an UnregisterNotificationEvent routine is defined as follows.
old-location: audio\unregisternotificationevent.htm
tech.root: audio
ms.assetid: 525e2dd9-68e1-468d-895e-d9f57372d619
ms.date: 04/08/2019
keywords: ["PUNREGISTER_NOTIFICATION_EVENT callback function"]
ms.keywords: PUNREGISTER_NOTIFICATION_EVENT, PUNREGISTER_NOTIFICATION_EVENT callback, UnregisterNotificationEvent, UnregisterNotificationEvent callback function [Audio Devices], aud-prop2_3f7488ae-5744-422e-871f-54dc2fd63bc2.xml, audio.unregisternotificationevent, hdaudio/UnregisterNotificationEvent
f1_keywords:
 - "hdaudio/UnregisterNotificationEvent"
 - "UnregisterNotificationEvent"
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL.
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Hdaudio.h
api_name:
- UnregisterNotificationEvent
targetos: Windows
req.typenames: 
---

# PUNREGISTER_NOTIFICATION_EVENT callback function


## -description


The <i>UnregisterNotificationEvent</i> routine deletes the registration of an event that was previously registered by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pregister_notification_event">RegisterNotificationEvent</a>.

The function pointer type for an <i>UnregisterNotificationEvent</i> routine is defined as follows.


## -parameters




### -param _context [in]

Specifies the context value from the Context member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a> structure.


### -param Handle [in]

Handle that identifies the DMA engine. This handle value was obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_capture_dma_engine">AllocateCaptureDmaEngine</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_render_dma_engine">AllocateRenderDmaEngine</a>.


### -param NotificationEvent [in]

A pointer to a kernel event that was previously registered for DMA progress notification with a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pregister_notification_event">RegisterNotificationEvent</a>.


## -returns



<i>UnregisterNotificationEvent</i> returns STATUS_SUCCESS if the call successfully unregisters the notification event. Otherwise, the routine returns STATUS_INVALID_PARAMETER to indicate that the specified callback routine and context are not valid. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_capture_dma_engine">AllocateCaptureDmaEngine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_render_dma_engine">AllocateRenderDmaEngine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pregister_notification_event">RegisterNotificationEvent</a>
 

[hdaudio.h](../hdaudio/index.md)
 

