---
UID: NC:hdaudio.PUNREGISTER_NOTIFICATION_EVENT
title: PUNREGISTER_NOTIFICATION_EVENT
author: windows-driver-content
description: The UnregisterNotificationEvent routine deletes the registration of an event that was previously registered by a call to RegisterNotificationEvent.The function pointer type for an UnregisterNotificationEvent routine is defined as follows.
old-location: audio\unregisternotificationevent.htm
old-project: audio
ms.assetid: 525e2dd9-68e1-468d-895e-d9f57372d619
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: PUNREGISTER_NOTIFICATION_EVENT, UnregisterNotificationEvent, UnregisterNotificationEvent callback function [Audio Devices], aud-prop2_3f7488ae-5744-422e-871f-54dc2fd63bc2.xml, audio.unregisternotificationevent, hdaudio/UnregisterNotificationEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Hdaudio.h
api_name:
-	UnregisterNotificationEvent
product: Windows
targetos: Windows
req.typenames: SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
---

# PUNREGISTER_NOTIFICATION_EVENT callback


## -description


The <i>UnregisterNotificationEvent</i> routine deletes the registration of an event that was previously registered by a call to <a href="..\hdaudio\nc-hdaudio-pregister_notification_event.md">RegisterNotificationEvent</a>.

The function pointer type for an <i>UnregisterNotificationEvent</i> routine is defined as follows.


## -prototype


````
PUNREGISTER_NOTIFICATION_EVENT UnregisterNotificationEvent;

typedef NTSTATUS UnregisterNotificationEvent(
  _In_ PVOID   _context,
  _In_ HANDLE  Handle,
  _In_ PKEVENT NotificationEvent
)
{ ... }
````


## -parameters




### -param _context [in]

Specifies the context value from the Context member of the <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a> structure.


### -param Handle [in]

Handle that identifies the DMA engine. This handle value was obtained from a previous call to <a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a> or <a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>.


### -param NotificationEvent [in]

A pointer to a kernel event that was previously registered for DMA progress notification with a call to <a href="..\hdaudio\nc-hdaudio-pregister_notification_event.md">RegisterNotificationEvent</a>.


## -returns



<i>UnregisterNotificationEvent</i> returns STATUS_SUCCESS if the call successfully unregisters the notification event. Otherwise, the routine returns STATUS_INVALID_PARAMETER to indicate that the specified tag is not valid. 




## -see-also

<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a>



<a href="..\hdaudio\nc-hdaudio-pregister_notification_event.md">RegisterNotificationEvent</a>



<a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>



<a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a>



 

 


