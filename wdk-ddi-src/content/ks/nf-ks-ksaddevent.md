---
UID: NF:ks.KsAddEvent
title: KsAddEvent function
author: windows-driver-content
description: The KsAddEvent function adds an event to Object's event list.
old-location: stream\ksaddevent.htm
old-project: stream
ms.assetid: 75c909b1-8eb5-4887-b528-d3ac465ee12b
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsAddEvent function [Streaming Media Devices], avfunc_20b264e1-c7ad-4b24-bff3-996b9d478a44.xml, stream.ksaddevent, KsAddEvent, ks/KsAddEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsAddEvent
product: Windows
targetos: Windows
req.typenames: 
---

# KsAddEvent function


## -description


The<b> KsAddEvent </b>function adds an event to <i>Object</i>'s event list.


## -syntax


````
void KsAddEvent(
  _In_ PVOID          Object,
  _In_ PKSEVENT_ENTRY EventEntry
);
````


## -parameters




### -param Object [in]

The object to which to add the event.


### -param EventEntry [in]

A pointer to an <a href="..\ks\ns-ks-_ksevent_entry.md">KSEVENT_ENTRY</a> structure describing the event to add to <i>Object</i>.


## -returns



None




## -remarks



Minidrivers typically do not call this routine directly; instead, they use <a href="..\ks\nf-ks-ksfilteraddevent.md">KsFilterAddEvent</a> or <a href="..\ks\nf-ks-kspinaddevent.md">KsPinAddEvent</a>. 

After events have been added to the event list, these events can be generated as data events by a <b>Ks</b><i>Xxx</i><b>GenerateEvents</b> call. Typecasting of the object (a filter or pin) to PVOID must be provided by the caller.




## -see-also

<a href="..\ks\nf-ks-kspinaddevent.md">KsPinAddEvent</a>



<a href="..\ks\nf-ks-ksdefaultaddeventhandler.md">KsDefaultAddEventHandler</a>



<a href="..\ks\nf-ks-ksgenerateevents.md">KsGenerateEvents</a>



<a href="..\ks\ns-ks-_ksevent_entry.md">KSEVENT_ENTRY</a>



<a href="..\ks\nf-ks-ksfilteraddevent.md">KsFilterAddEvent</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsAddEvent function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

