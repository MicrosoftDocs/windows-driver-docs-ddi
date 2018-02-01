---
UID: NF:ks.KsFilterAddEvent
title: KsFilterAddEvent function
author: windows-driver-content
description: The KsFilterAddEvent function adds an event to Filter's event list.
old-location: stream\ksfilteraddevent.htm
old-project: stream
ms.assetid: e93491c1-bd6d-4d89-b55f-10439b0f5eec
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/KsFilterAddEvent, avfunc_a00691e6-cae6-40ae-9776-1b6d09e01d73.xml, stream.ksfilteraddevent, KsFilterAddEvent, KsFilterAddEvent function [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KsFilterAddEvent
product: Windows
targetos: Windows
req.typenames: 
---

# KsFilterAddEvent function


## -description


The<b> KsFilterAddEvent</b> function adds an event to <i>Filter</i>'s event list.


## -syntax


````
void _inline KsFilterAddEvent(
  _In_ PKSFILTER      Filter,
  _In_ PKSEVENT_ENTRY EventEntry
);
````


## -parameters




### -param Filter [in]

<i>A pointer</i> to a <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure representing the filter to which to add a specified event.


### -param EventEntry [in]

<i>A pointer</i> to an <a href="..\ks\ns-ks-_ksevent_entry.md">KSEVENT_ENTRY</a> structure describing the event to add to <i>Filter</i>.


## -returns


None



## -remarks


This function is an inline function call to <a href="..\ks\nf-ks-ksaddevent.md">KsAddEvent</a>.



## -see-also

<a href="..\ks\ns-ks-_ksevent_entry.md">KSEVENT_ENTRY</a>

<a href="..\ks\nf-ks-ksaddevent.md">KsAddEvent</a>

<a href="..\ks\nf-ks-ksgenerateevents.md">KsGenerateEvents</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterAddEvent function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

