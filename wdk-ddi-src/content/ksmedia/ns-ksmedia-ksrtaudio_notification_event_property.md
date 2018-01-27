---
UID: NS:ksmedia.KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY
title: KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY
author: windows-driver-content
description: The KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY structure appends an event handle to a KSPROPERTY structure
old-location: audio\ksrtaudio_notification_event_property.htm
old-project: audio
ms.assetid: 364db984-1107-4381-ade3-413e238b9796
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY structure [Audio Devices], ksmedia/PKSRTAUDIO_NOTIFICATION_EVENT_PROPERTY, aud-prop_0c408e4a-d94e-4458-9b31-da185dc42747.xml, *PKSRTAUDIO_NOTIFICATION_EVENT_PROPERTY, KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY, audio.ksrtaudio_notification_event_property, PKSRTAUDIO_NOTIFICATION_EVENT_PROPERTY structure pointer [Audio Devices], PKSRTAUDIO_NOTIFICATION_EVENT_PROPERTY, ksmedia/KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	ksmedia.h
apiname: 
-	KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY
product: Windows
targetos: Windows
req.typenames: *PKSRTAUDIO_NOTIFICATION_EVENT_PROPERTY, KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY
---

# KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY structure


## -description


The KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY structure appends an event handle to a <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure


## -syntax


````
typedef struct {
  KSPROPERTY Property;
  HANDLE     NotificationEvent;
} KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY, *PKSRTAUDIO_NOTIFICATION_EVENT_PROPERTY;
````


## -struct-fields




### -field Property

A KSPROPERTY structure that the client initializes appropriately prior to calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff537385">KSPROPERTY_RTAUDIO_REGISTER_NOTIFICATION_EVENT</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff537387">KSPROPERTY_RTAUDIO_UNREGISTER_NOTIFICATION_EVENT</a>.


### -field NotificationEvent

Specifies a user-mode event handle to be registered or unregistered for event notifications.


## -remarks


The KSPROPERTY_RTAUDIO_REGISTER_NOTIFICATION_EVENT and KSPROPERTY_RTAUDIO_UNREGISTER_NOTIFICATION_EVENT property requests use the KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY structure to pass a user-mode event handle from the client to the driver.

The <b>NotificationEvent</b> member is a user-mode event handle that, when registered, receives signals as buffer DMA progresses.  The notification cabability is only available upon a successful call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff537374">KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION</a>.



## -see-also

<b>KSPROPERTY_RTAUDIO_UNREGISTER_NOTIFICATION_EVENT</b>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537385">KSPROPERTY_RTAUDIO_REGISTER_NOTIFICATION_EVENT</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537374">KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION</a>

<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

