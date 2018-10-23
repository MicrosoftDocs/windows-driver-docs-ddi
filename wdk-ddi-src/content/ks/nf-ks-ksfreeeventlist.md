---
UID: NF:ks.KsFreeEventList
title: KsFreeEventList function
author: windows-driver-content
description: The KsFreeEventList function handles freeing all events from a specified list, with the assumption that these events are composed of KSEVENT_ENTRY structures. This function can only be called at PASSIVE_LEVEL.
old-location: stream\ksfreeeventlist.htm
tech.root: stream
ms.assetid: 3ccbbf07-7d8d-423a-b50d-d202e1cb7ab2
ms.date: 04/23/2018
ms.keywords: KsFreeEventList, KsFreeEventList function [Streaming Media Devices], ks/KsFreeEventList, ksfunc_b9315995-1d55-4edc-97b4-4fb6ad5631a2.xml, stream.ksfreeeventlist
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
-	KsFreeEventList
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsFreeEventList function


## -description


The <b>KsFreeEventList</b> function handles freeing all events from a specified list, with the assumption that these events are composed of <b>KSEVENT_ENTRY</b> structures. This function can only be called at PASSIVE_LEVEL.


## -parameters




### -param FileObject [in]

Specifies the file object passed to the removal function for context information. The file object associated is used to compare against the file object originally specified when enabling the event. This allows a single event list to be used for multiple clients differentiated by file objects.


### -param EventsList [in, out]

Points to the head of the list of KSEVENT_ENTRY items to be freed. If any events on the list are currently being disabled, they are passed over. If any new elements are added to the list while it is being processed, they may not be freed.


### -param EventsFlags [in]

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561784">KSEVENTS_LOCKTYPE</a> flag specifying the type of exclusion lock to be used in accessing the event list. If no flag is set, then no lock is taken.


### -param EventsLock [in]

Used to synchronize access to an element on the list. After the element has been accessed, it is marked as being deleted so subsequent removal requests fail. The lock is then released after calling the removal function, if any. The removal function must synchronize with event generation before actually removing the element from the list.


## -returns



None




## -remarks



The <b>KsFreeEventList</b> function calls the remove handler, and then it calls <b>KsDiscardEvent</b> for each event. It does not assume that the caller is the event owner.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561697">KsDiscardEvent</a>
 

 

