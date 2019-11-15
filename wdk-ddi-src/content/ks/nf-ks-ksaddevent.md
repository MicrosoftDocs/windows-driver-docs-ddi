---
UID: NF:ks.KsAddEvent
title: KsAddEvent function (ks.h)
description: The KsAddEvent function adds an event to Object's event list.
old-location: stream\ksaddevent.htm
tech.root: stream
ms.assetid: 75c909b1-8eb5-4887-b528-d3ac465ee12b
ms.date: 04/23/2018
ms.keywords: KsAddEvent, KsAddEvent function [Streaming Media Devices], avfunc_20b264e1-c7ad-4b24-bff3-996b9d478a44.xml, ks/KsAddEvent, stream.ksaddevent
ms.topic: function
f1_keywords:
 - "ks/KsAddEvent"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsAddEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsAddEvent function


## -description


The<b> KsAddEvent </b>function adds an event to <i>Object</i>'s event list.


## -parameters




### -param Object [in]

The object to which to add the event.


### -param EventEntry [in]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksevent_entry">KSEVENT_ENTRY</a> structure describing the event to add to <i>Object</i>.


## -remarks



Minidrivers typically do not call this routine directly; instead, they use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfilteraddevent">KsFilterAddEvent</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspinaddevent">KsPinAddEvent</a>. 

After events have been added to the event list, these events can be generated as data events by a <b>Ks</b><i>Xxx</i><b>GenerateEvents</b> call. Typecasting of the object (a filter or pin) to PVOID must be provided by the caller.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksevent_entry">KSEVENT_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksdefaultaddeventhandler">KsDefaultAddEventHandler</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfilteraddevent">KsFilterAddEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgenerateevents">KsGenerateEvents</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspinaddevent">KsPinAddEvent</a>
 

 

