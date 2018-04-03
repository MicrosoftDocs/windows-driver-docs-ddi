---
UID: NF:ks.KsGenerateDataEvent
title: KsGenerateDataEvent function
author: windows-driver-content
description: The KsGenerateDataEvent function generates one of the standard event notifications when given an event entry structure and callback data.
old-location: stream\ksgeneratedataevent.htm
old-project: stream
ms.assetid: 3ba49134-e144-4212-9ef7-e16b9d5f90ea
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsGenerateDataEvent, KsGenerateDataEvent function [Streaming Media Devices], ks/KsGenerateDataEvent, ksfunc_4e7efb50-d6c2-45b5-9b44-5c3d48e91933.xml, stream.ksgeneratedataevent
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
-	KsGenerateDataEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsGenerateDataEvent function


## -description


The <b>KsGenerateDataEvent</b> function generates one of the standard event notifications when given an event entry structure and callback data. This allows a device to determine when event notifications should be generated, yet still use this helper function to perform the actual notification.


## -parameters




### -param EventEntry [in]

Specifies the event entry structure that references the event data. The information is used to determine what type of notification to perform. If the notification type is not one of the predefined standards, an error is returned. In the case of a single, nonrecurring event, this entry will be invalid when returned from the function. Therefore, any code that enumerates a list of events must preincrement to acquire the next event in the list before passing this event to the function.


### -param DataSize [in]

Specifies the size in bytes of the <i>Data</i> parameter passed.


### -param Data [in]

Points to data to be passed to the client callback. This data is copied to one of the preallocated buffer slots set up when the event was enabled. The size of the data must be less than whatever was originally allocated or the event will fail.


## -returns



The <b>KsGenerateDataEvent</b> function returns STATUS_SUCCESS if successful, or if unsuccessful it returns an exception or memory error.




## -remarks



It is assumed that the event list lock has been acquired before this function is called. This function can result in a call to the <b>RemoveHandler</b> for the event entry. Therefore, the function must not be called at higher than the IRQ level of the lock, or the <b>Remove</b> function must be able to handle being called at such an IRQ level.

This function is specifically for events that pass data back through a callback to a client.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560992">KSBUFFER_ITEM</a>
 

 

