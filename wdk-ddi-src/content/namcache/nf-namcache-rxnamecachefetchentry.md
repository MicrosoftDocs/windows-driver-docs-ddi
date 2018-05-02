---
UID: NF:namcache.RxNameCacheFetchEntry
title: RxNameCacheFetchEntry function
author: windows-driver-content
description: RxNameCacheFetchEntry looks for a match with a specified name string for a NAME_CACHE entry.
old-location: ifsk\rxnamecachefetchentry.htm
old-project: ifsk
ms.assetid: 1f4c50a8-2eee-46c6-8ca0-f5858d227922
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: RxNameCacheFetchEntry, RxNameCacheFetchEntry function [Installable File System Drivers], ifsk.rxnamecachefetchentry, namcache/RxNameCacheFetchEntry, rxref_8e34b551-b8ee-44e9-a0ff-bbc680e44ad6.xml
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
-	RxNameCacheFetchEntry
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxNameCacheFetchEntry function


## -description


<b>RxNameCacheFetchEntry</b> looks for a match with a specified name string for a NAME_CACHE entry.


## -parameters




### -param NameCacheCtl [in]

A pointer to the NAME_CACHE_CONTROL structure to scan.


### -param Name [in]

A pointer to the Unicode string that contains the name to match.


## -returns



<b>RxNameCacheFetchEntry </b>returns a pointer to the matching NAME_CACHE structure if a match was found, or <b>NULL</b> if the match failed. 




## -remarks



<b>RxNameCacheFetchEntry</b> looks for a match in the name cache active list for the specified <i>Name</i> parameter. If the name is found, the entry is removed from the name cache active list and a pointer to the NAME_CACHE structure is returned. Otherwise, <b>NULL</b> is returned.

The NAME_CACHE entry is removed from the active list to avoid possible problems with another thread that is trying to update the same entry, or observing that it expired and putting it on the free list. It is possible to get multiple entries with the same name by different threads, but eventually they will expire.

If a matching NAME_CACHE entry is found, no check is made for expiration. The caller must check for expiration because it might want to take some special action.

As a aside effect as the name cache active list is scanned, any non-matching entries that have expired are put on the free list. The name cache lock is acquired to protect this operation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554552">RxNameCacheActivateEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554558">RxNameCacheCheckEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554565">RxNameCacheCreateEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554569">RxNameCacheExpireEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554570">RxNameCacheExpireEntryWithShortName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554575">RxNameCacheFinalize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554579">RxNameCacheFreeEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554586">RxNameCacheInitialize</a>
 

 

