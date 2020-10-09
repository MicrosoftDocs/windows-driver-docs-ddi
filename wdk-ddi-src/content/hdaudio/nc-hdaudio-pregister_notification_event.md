---
UID: NC:hdaudio.PREGISTER_NOTIFICATION_EVENT
title: PREGISTER_NOTIFICATION_EVENT (hdaudio.h)
description: The RegisterNotificationEvent routine registers a kernel event so that it can receive DMA progress notifications.The function pointer type for a RegisterNotificationEvent routine is defined as follows.
old-location: audio\registernotificationevent.htm
tech.root: audio
ms.assetid: 44702d79-80ac-411f-ae47-bf60b9cb541d
ms.date: 05/08/2018
keywords: ["PREGISTER_NOTIFICATION_EVENT callback function"]
ms.keywords: PREGISTER_NOTIFICATION_EVENT, PREGISTER_NOTIFICATION_EVENT callback, RegisterNotificationEvent, RegisterNotificationEvent callback function [Audio Devices], aud-prop2_fa7a1f01-c553-40df-971b-932f8da48353.xml, audio.registernotificationevent, hdaudio/RegisterNotificationEvent
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PREGISTER_NOTIFICATION_EVENT
 - hdaudio/PREGISTER_NOTIFICATION_EVENT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Hdaudio.h
api_name:
 - RegisterNotificationEvent
---

# PREGISTER_NOTIFICATION_EVENT callback function


## -description

The <i>RegisterNotificationEvent</i> routine registers a kernel event so that it can receive DMA progress notifications.

The function pointer type for a <i>RegisterNotificationEvent</i> routine is defined as follows.

## -parameters

### -param _context 

[in]
Specifies the context value from the Context member of the <a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a> structure.

### -param Handle 

[in]
Handle that identifies the DMA engine. This handle value was obtained from a previous call to <a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_capture_dma_engine">AllocateCaptureDmaEngine</a> or <a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_render_dma_engine">AllocateRenderDmaEngine</a>.

### -param NotificationEvent 

[in]
A pointer to a kernel event that must be notified as DMA progresses.  Depending on the notification count parameter that is used with <a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_dma_buffer_with_notification">AllocateDmaBufferWithNotification</a>, the registered event is signaled one or two times for every time that the DMA passes through the audio buffer.

## -returns

<i>RegisterNotificationEvent</i> returns STATUS_SUCCESS if the call successfully registers the event. Otherwise, the routine returns STATUS_INSUFFICIENT_RESOURCES to indicate that there are insufficient resources that are available to complete the operation.

## -remarks

<i>RegisterNotificationEvent</i> registers a kernel event with the HD Audio bus driver.  The HD Audio bus driver maintains a list of registered notification events for each DMA engine, and signals them every time that the engine receives an IOC interrupt.  Events are unregistered by using <a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-punregister_notification_event">UnregisterNotificationEvent</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_capture_dma_engine">AllocateCaptureDmaEngine</a>



<a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_dma_buffer_with_notification">AllocateDmaBufferWithNotification</a>



<a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_render_dma_engine">AllocateRenderDmaEngine</a>



<a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a>



<a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-punregister_notification_event">UnregisterNotificationEvent</a>