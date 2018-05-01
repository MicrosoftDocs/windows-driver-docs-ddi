---
UID: NF:namcache.RxNameCacheFreeEntry
title: RxNameCacheFreeEntry function
author: windows-driver-content
description: RxNameCacheFreeEntry releases the storage for a NAME_CACHE entry and decrements the count of the NAME_CACHE cache entries associated with a NAME_CACHE_CONTROL structure.
old-location: ifsk\rxnamecachefreeentry.htm
old-project: ifsk
ms.assetid: c1adef80-b8f2-49bb-9254-b89c8d1af220
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: RxNameCacheFreeEntry, RxNameCacheFreeEntry function [Installable File System Drivers], ifsk.rxnamecachefreeentry, namcache/RxNameCacheFreeEntry, rxref_ca0b7c99-59df-4a51-b28b-4c369b451741.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: namcache.h
req.include-header: Namcache.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	namcache.h
api_name:
-	RxNameCacheFreeEntry
product: Windows
targetos: Windows
req.typenames: 
---

# RxNameCacheFreeEntry function


## -description


<b>RxNameCacheFreeEntry</b> releases the storage for a NAME_CACHE entry and decrements the count of the NAME_CACHE cache entries associated with a NAME_CACHE_CONTROL structure. 


## -parameters




### -param NameCacheCtl [in]

A pointer to the NAME_CACHE_CONTROL structure for the name cache.


### -param NameCache [in]

A pointer to the NAME_CACHE structure to free.


## -returns



None




## -remarks



The <b>RxNameCacheFreeEntry</b> routine assumes that the name cache entry is not on either the free or active list.

The <b>RxNameCacheFreeEntry</b> routine frees memory allocated for the name buffer if the name buffer for this name cache entry is not <b>NULL</b>. This routine will then free memory used for the NAME_CACHE entry. Then, the count of name cache entries on <i>NameCacheCtl</i> is decremented.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554552">RxNameCacheActivateEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554558">RxNameCacheCheckEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554565">RxNameCacheCreateEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554569">RxNameCacheExpireEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554570">RxNameCacheExpireEntryWithShortName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554573">RxNameCacheFetchEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554575">RxNameCacheFinalize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554586">RxNameCacheInitialize</a>
 

 

