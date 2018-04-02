---
UID: NS:ksmedia.KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY
title: KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY
author: windows-driver-content
description: The KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY structure appends an event handle to a KSPROPERTY structure
old-location: audio\ksrtaudio_notification_event_property.htm
old-project: audio
ms.assetid: 364db984-1107-4381-ade3-413e238b9796
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: "*PKSRTAUDIO_NOTIFICATION_EVENT_PROPERTY, KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY, KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY structure [Audio Devices], PKSRTAUDIO_NOTIFICATION_EVENT_PROPERTY, PKSRTAUDIO_NOTIFICATION_EVENT_PROPERTY structure pointer [Audio Devices], aud-prop_0c408e4a-d94e-4458-9b31-da185dc42747.xml, audio.ksrtaudio_notification_event_property, ksmedia/KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY, ksmedia/PKSRTAUDIO_NOTIFICATION_EVENT_PROPERTY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later Windows operating systems.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY
product: Windows
targetos: Windows
req.typenames: KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY, *PKSRTAUDIO_NOTIFICATION_EVENT_PROPERTY
---

# KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY structure


## -description


The KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY structure appends an event handle to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure


## -struct-fields




### -field Property

A KSPROPERTY structure that the client initializes appropriately prior to calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff537385">KSPROPERTY_RTAUDIO_REGISTER_NOTIFICATION_EVENT</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff537387">KSPROPERTY_RTAUDIO_UNREGISTER_NOTIFICATION_EVENT</a>.


### -field NotificationEvent

Specifies a user-mode event handle to be registered or unregistered for event notifications.


## -remarks



The KSPROPERTY_RTAUDIO_REGISTER_NOTIFICATION_EVENT and KSPROPERTY_RTAUDIO_UNREGISTER_NOTIFICATION_EVENT property requests use the KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY structure to pass a user-mode event handle from the client to the driver.

The <b>NotificationEvent</b> member is a user-mode event handle that, when registered, receives signals as buffer DMA progresses.  The notification cabability is only available upon a successful call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff537374">KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537374">KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537385">KSPROPERTY_RTAUDIO_REGISTER_NOTIFICATION_EVENT</a>



<b>KSPROPERTY_RTAUDIO_UNREGISTER_NOTIFICATION_EVENT</b>
 

 

