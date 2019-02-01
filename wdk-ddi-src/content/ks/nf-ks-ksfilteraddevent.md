---
UID: NF:ks.KsFilterAddEvent
title: KsFilterAddEvent function (ks.h)
description: The KsFilterAddEvent function adds an event to Filter's event list.
old-location: stream\ksfilteraddevent.htm
tech.root: stream
ms.assetid: e93491c1-bd6d-4d89-b55f-10439b0f5eec
ms.date: 04/23/2018
ms.keywords: KsFilterAddEvent, KsFilterAddEvent function [Streaming Media Devices], avfunc_a00691e6-cae6-40ae-9776-1b6d09e01d73.xml, ks/KsFilterAddEvent, stream.ksfilteraddevent
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KsFilterAddEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsFilterAddEvent function


## -description


The<b> KsFilterAddEvent</b> function adds an event to <i>Filter</i>'s event list.


## -parameters




### -param Filter [in]

<i>A pointer</i> to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a> structure representing the filter to which to add a specified event.


### -param EventEntry [in]

<i>A pointer</i> to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff561853">KSEVENT_ENTRY</a> structure describing the event to add to <i>Filter</i>.


## -returns



None




## -remarks



This function is an inline function call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff560931">KsAddEvent</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561853">KSEVENT_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560931">KsAddEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562597">KsGenerateEvents</a>
 

 

