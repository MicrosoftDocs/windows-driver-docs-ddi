---
UID: NC:ks.PFNKSADDEVENT
title: PFNKSADDEVENT
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniAddEvent routine is called when a client registers to be notified of an event. This routine is optional.
old-location: stream\avstrminiaddevent.htm
old-project: stream
ms.assetid: ff80bbc7-93b1-4319-a549-f896ce0f4611
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: AVStrMiniAddEvent, AVStrMiniAddEvent routine [Streaming Media Devices], PFNKSADDEVENT, avstclbk_31147072-c3de-4b02-9fb1-b7f67765acc4.xml, ks/AVStrMiniAddEvent, stream.avstrminiaddevent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
-	UserDefined
api_location:
-	ks.h
api_name:
-	AVStrMiniAddEvent
product: Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---

# PFNKSADDEVENT callback


## -description


An AVStream minidriver's <i>AVStrMiniAddEvent</i> routine is called when a client registers to be notified of an event. This routine is optional.


## -parameters




### -param Irp [in]

Specifies the IRP describing the event add request.


### -param EventData [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561750">KSEVENTDATA</a> structure describing the notification method for this event.


### -param *EventEntry [in]

Pointer to an AVStream-generated <a href="https://msdn.microsoft.com/library/windows/hardware/ff561853">KSEVENT_ENTRY</a> structure describing how the event is triggered.


## -returns



<i>AVStrMiniAddEvent</i> should return STATUS_SUCCESS or an error specific to the event being enabled.  




## -remarks



If you do not provide an add event handler, AVStream adds the event to the object list. See <a href="https://msdn.microsoft.com/7add2055-8d3f-432d-8aa1-44459ac197dd">Event Handling in AVStream</a>.

Frequently this callback implements vendor-specific behavior and then calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff562525">KsFilterAddEvent</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff563490">KsPinAddEvent</a>. The minidriver passes the <i>EventEntry</i> pointer received here in calls to <i>KsFilterAddEvent</i> or <i>KsPinAddEvent</i>.

The minidriver specifies this routine's address in the <b>AddHandler</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561862">KSEVENT_ITEM</a> structure. <a href="https://msdn.microsoft.com/7add2055-8d3f-432d-8aa1-44459ac197dd">Event Handling in AVStream</a> describes how the minidriver provides this structure to the class driver.

If an AVStream minidriver specifies <b>AddHandler</b> as non-NULL, AVStream does not add the item to the object's event list. If minidriver specifies an <b>AddHandler</b> and does not add the event to the object's event list through <b>KsDefaultAddEventHandler()</b> or a <b>Ks*AddEvent </b>call, the minidriver is responsible for cleaning up the event.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556361">AVStrMiniRemoveEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560990">KSAUTOMATION_TABLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561750">KSEVENTDATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561853">KSEVENT_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561862">KSEVENT_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562525">KsFilterAddEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562541">KsFilterGenerateEvents</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563490">KsPinAddEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563500">KsPinGenerateEvents</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSADDEVENT routine%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

