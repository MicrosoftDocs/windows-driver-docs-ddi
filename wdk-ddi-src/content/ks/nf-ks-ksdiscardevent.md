---
UID: NF:ks.KsDiscardEvent
title: KsDiscardEvent function
author: windows-driver-content
description: The KsDiscardEvent function discards the memory used by an event entry after the objects have been dereferenced.
old-location: stream\ksdiscardevent.htm
old-project: stream
ms.assetid: 14aaf96a-4d1f-4e4a-9fed-e493090157b8
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsDiscardEvent, KsDiscardEvent function [Streaming Media Devices], ks/KsDiscardEvent, ksfunc_553391e5-343a-4cc7-9bc5-99971cff2fcd.xml, stream.ksdiscardevent
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsDiscardEvent
product: Windows
targetos: Windows
req.typenames: 
---

# KsDiscardEvent function


## -description


The <b>KsDiscardEvent</b> function discards the memory used by an event entry after the objects have been dereferenced. The function can be called when manually disabling events that have not been disabled by the event owner (by calling the <b>KsFreeEventList</b> function to disable events). For example, the function can be called when asynchronously enabling an event fails and the event entry needs to be discarded.


## -parameters




### -param EventEntry [in]

Specifies the pointer to the entry to discard. This pointer is no longer valid after a successful call to this function.


## -returns



None




## -remarks



Typically, the <b>KsDiscardEvent</b> function is automatically called by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561694">KsDisableEvent</a> function when a request to disable an event occurs, or by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562561">KsFreeEventList</a> function when a request to free a list of events occurs. This function can only be called at PASSIVE_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561694">KsDisableEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562561">KsFreeEventList</a>
 

 

