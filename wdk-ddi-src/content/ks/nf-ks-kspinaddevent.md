---
UID: NF:ks.KsPinAddEvent
title: KsPinAddEvent function
author: windows-driver-content
description: The KsPinAddEvent function adds a specified event to Pin's event list.
old-location: stream\kspinaddevent.htm
old-project: stream
ms.assetid: 1bb34062-f092-41a4-8d59-6937be7b5639
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsPinAddEvent, KsPinAddEvent function [Streaming Media Devices], avfunc_2291126f-31dd-4e37-a082-97f24e8b5bd9.xml, ks/KsPinAddEvent, stream.kspinaddevent
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
-	KsPinAddEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPinAddEvent function


## -description


The<b> KsPinAddEvent </b>function adds a specified event to <i>Pin</i>'s event list.


## -parameters




### -param Pin [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> structure to which to add a specified event.


### -param EventEntry [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561853">KSEVENT_ENTRY</a> structure describing the event to add to <i>Pin</i>.


## -returns



None




## -remarks



This function is an inline function call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff560931">KsAddEvent</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561853">KSEVENT_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560931">KsAddEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561662">KsDefaultAddEventHandler</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562541">KsFilterGenerateEvents</a>



<b>KsGenerateEvents</b>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563500">KsPinGenerateEvents</a>
 

 

