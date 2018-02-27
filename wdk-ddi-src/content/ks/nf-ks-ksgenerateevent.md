---
UID: NF:ks.KsGenerateEvent
title: KsGenerateEvent function
author: windows-driver-content
description: The KsGenerateEvent function generates a standard event notification given an event entry structure.
old-location: stream\ksgenerateevent.htm
old-project: stream
ms.assetid: 4f142e5f-7d8a-47e0-8757-8c6e527a2472
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsGenerateEvent, KsGenerateEvent function [Streaming Media Devices], ks/KsGenerateEvent, ksfunc_929fd3d4-2f02-4106-b8cd-25c3fb13ba05.xml, stream.ksgenerateevent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: Any level (See Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsGenerateEvent
product: Windows
targetos: Windows
req.typenames: 
---

# KsGenerateEvent function


## -description


The <b>KsGenerateEvent</b> function generates a standard event notification given an event entry structure.


## -syntax


````
NTSTATUS KsGenerateEvent(
  _In_ PKSEVENT_ENTRY EventEntry
);
````


## -parameters




### -param EventEntry [in]

Specifies the event entry structure that references the event data. The information is used to determine what type of notification to perform. If the notification type is not one of the predefined standards, an error is returned. In the case of a single, nonrecurring event, this entry will be invalid on returning from the function. Therefore, any code that enumerates a list of events must preincrement to acquire the next event in the list before passing this event to the function.


## -returns



The <b>KsGenerateEvent</b> function returns STATUS_SUCCESS if successful, or if unsuccessful it returns an exception or memory error.




## -remarks



A device determines when event notifications are generated using the <a href="..\ks\ns-ks-_ksevent_entry.md">KSEVENT_ENTRY</a> structure, then uses this function to perform the actual notification. <b>KsGenerateEvent</b> can be called at any IRQL. If called above DISPATCH_LEVEL, signaling of the event will be performed asynchronously in a DPC.




## -see-also

<a href="..\ks\nf-ks-ksfiltergenerateevents.md">KsFilterGenerateEvents</a>



<a href="..\ks\nf-ks-kspingenerateevents.md">KsPinGenerateEvents</a>



<a href="..\ks\nf-ks-kspinaddevent.md">KsPinAddEvent</a>



<a href="..\ks\nf-ks-ksfilteraddevent.md">KsFilterAddEvent</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGenerateEvent function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

