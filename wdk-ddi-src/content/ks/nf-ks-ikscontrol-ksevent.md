---
UID: NF:ks.IKsControl.KsEvent
title: IKsControl::KsEvent method
author: windows-driver-content
description: The IKsControl::KsEvent method enables or disables an event, together with any other defined support operations available on an event set.
old-location: stream\ikscontrol_ksevent2.htm
old-project: stream
ms.assetid: 9e4b86cf-308f-4d9b-be28-966312dc4e43
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsEvent method [Streaming Media Devices], IKsControl interface, IKsControl, ks/IKsControl::KsEvent, KsEvent, IKsControl interface [Streaming Media Devices], KsEvent method, IKsControl::KsEvent, stream.ikscontrol_ksevent2, KsEvent method [Streaming Media Devices], avintfc_359de56d-5fcc-47ea-838c-cd110493856c.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ks.h
req.include-header: Ks.h
req.target-type: DesktopMobile
req.target-min-winverclnt: 
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
req.lib: ks.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	ks.h
apiname:
-	IKsControl.KsEvent
product: Windows
targetos: Windows
req.typenames: 
---

# IKsControl::KsEvent method


## -description


The <b>IKsControl::KsEvent</b> method enables or disables an event, together with any other defined support operations available on an event set. 


## -syntax


````
NTSTATUS KsEvent(
   PKSEVENT Event,
   ULONG    EventLength,
   PVOID    EventData,
   ULONG    DataLength,
   ULONG    BytesReturned
);
````


## -parameters




### -param Event

Pointer to a <a href="..\ks\nf-ks-ikscontrol-ksevent.md">KSEVENT</a> structure that describes an event to enable the event and <b>NULL</b> to disable the event.


### -param EventLength

Specifies size, in bytes, of the buffer at <i>Event</i> when the event is enabled and zero when the event is disabled. 


### -param EventData

Pointer to a <a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a> structure that contains data for the event and buffer space that receives data for the event. 


### -param DataLength

Specifies size, in bytes, of the buffer at <i>EventData</i>. 


### -param BytesReturned

Pointer to a variable that receives the size, in bytes, of the data that <b>KsEvent</b> stores in the buffer at <i>EventData</i>. 


## -returns



The <b>IKsControl::KsEvent</b> method returns the same value that would be returned if the event had been sent by IOCTL.




## -remarks



To disable an event, set <i>Event</i> to <b>NULL</b>, <i>EventLength</i> to zero, and <i>EventData</i> to the pointer to the <a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a> structure that was previously used to enable the event.




## -see-also

<a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a>



<a href="..\ks\nf-ks-ikscontrol-ksevent.md">KSEVENT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsControl::KsEvent method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

