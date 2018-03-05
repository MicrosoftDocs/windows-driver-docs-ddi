---
UID: NF:portcls.IResourceList.NumberOfEntries
title: IResourceList::NumberOfEntries method
author: windows-driver-content
description: The NumberOfEntries method returns the number of resource items in the resource list.
old-location: audio\iresourcelist_numberofentries.htm
old-project: audio
ms.assetid: cb882170-5c8e-455d-89a6-b09ca77e63fb
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IResourceList, IResourceList interface [Audio Devices], NumberOfEntries method, IResourceList::NumberOfEntries, NumberOfEntries method [Audio Devices], NumberOfEntries method [Audio Devices], IResourceList interface, NumberOfEntries,IResourceList.NumberOfEntries, audio.iresourcelist_numberofentries, audmp-routines_65fc1416-83e5-4cb6-b362-3133affd5448.xml, portcls/IResourceList::NumberOfEntries
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
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
req.lib: portcls.h
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IResourceList.NumberOfEntries
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IResourceList::NumberOfEntries method


## -description


The <code>NumberOfEntries</code> method returns the number of resource items in the resource list.


## -syntax


````
ULONG NumberOfEntries(
    None
);
````


## -parameters






#### - None


## -returns



<code>NumberOfEntries</code> returns the number of items in the resource list.



