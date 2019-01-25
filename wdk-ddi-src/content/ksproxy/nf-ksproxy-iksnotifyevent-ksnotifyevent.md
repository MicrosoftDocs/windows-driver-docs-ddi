---
UID: NF:ksproxy.IKsNotifyEvent.KsNotifyEvent
title: IKsNotifyEvent::KsNotifyEvent (ksproxy.h)
description: The KsNotifyEvent method requests that the KS object that owns the given DirectShow event notify the calling application with the given parameters whenever action related to the event occurs.
old-location: stream\iksnotifyevent_ksnotifyevent.htm
tech.root: stream
ms.assetid: c0813b1a-402e-46ba-8d81-e31cdcbbb8dd
ms.date: 04/23/2018
ms.keywords: IKsNotifyEvent interface [Streaming Media Devices],KsNotifyEvent method, IKsNotifyEvent.KsNotifyEvent, IKsNotifyEvent::KsNotifyEvent, KsNotifyEvent, KsNotifyEvent method [Streaming Media Devices], KsNotifyEvent method [Streaming Media Devices],IKsNotifyEvent interface, ksproxy/IKsNotifyEvent::KsNotifyEvent, ksproxy_0fb6c49f-3aef-411d-90db-cf9a4186cdd9.xml, stream.iksnotifyevent_ksnotifyevent
ms.topic: method
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ksproxy.h
api_name:
-	IKsNotifyEvent.KsNotifyEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsNotifyEvent::KsNotifyEvent


## -description


<b>DirectX 9.0 and later versions only.</b>

The <b>KsNotifyEvent</b> method requests that the KS object that owns the given DirectShow event notify the calling application with the given parameters whenever action related to the event occurs. 


## -parameters




### -param Event [in]

Identifies the type of DirectShow event. 


### -param lParam1 [in]

Specifies the first data parameter for the event.


### -param lParam2 [in]

Specifies the second data parameter for the event.


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -see-also




<a href="https://go.microsoft.com/fwlink/p/?linkid=183549">IMediaEvent</a>
 

 

