---
UID: NF:namcache.RxNameCacheCreateEntry
title: RxNameCacheCreateEntry function (namcache.h)
description: RxNameCacheCreateEntry allocates and initializes a NAME_CACHE structure with the given name string.
old-location: ifsk\rxnamecachecreateentry.htm
tech.root: ifsk
ms.assetid: 1cfe2d2d-99fa-4dc2-b517-5026fd72d5d4
ms.date: 04/16/2018
keywords: ["RxNameCacheCreateEntry function"]
ms.keywords: RxNameCacheCreateEntry, RxNameCacheCreateEntry function [Installable File System Drivers], ifsk.rxnamecachecreateentry, namcache/RxNameCacheCreateEntry, rxref_a1245999-8aba-4012-a143-609517c2686b.xml
f1_keywords:
 - "namcache/RxNameCacheCreateEntry"
 - "RxNameCacheCreateEntry"
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- namcache.h
api_name:
- RxNameCacheCreateEntry
targetos: Windows
req.typenames: 
---

# RxNameCacheCreateEntry function


## -description


<b>RxNameCacheCreateEntry</b> allocates and initializes a NAME_CACHE structure with the given name string. 


## -parameters




### -param NameCacheCtl [in]

A pointer to the NAME_CACHE_CONTROL structure from which to allocate the entry.


### -param Name [in]

A pointer to the Unicode name string with which to initialize the name cache entry.


### -param CaseInsensitive [in]

A Boolean value that indicates if case insensitive comparions should be used when comparing the <i>Name</i> parameter. 


## -returns



<b>RxNameCacheCreateEntry </b>returns a pointer to the newly allocated NAME_CACHE structure on success or a <b>NULL</b> pointer if the allocation fails.




## -remarks



A network mini-redirector calls <b>RxNameCacheCreateEntry</b> to allocate and initialize a NAME_CACHE structure with the given name string. It is expected that the caller will then initialize any additional network mini-redirector elements of the name cache context, set the lifetime (in seconds) and the <b>Context</b> member of the NAME_CACHE structure and then put the entry on the name cache active list by calling <b>RxNameCacheActivateEntry</b>.

<b>RxNameCacheCreateEntry</b> will first attempt to reuse a NAME_CACHE entry on the free list, if one is available, before allocating a new NAME_CACHE entry. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecacheactivateentry">RxNameCacheActivateEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecachecheckentry">RxNameCacheCheckEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecacheexpireentry">RxNameCacheExpireEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecacheexpireentrywithshortname">RxNameCacheExpireEntryWithShortName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecachefetchentry">RxNameCacheFetchEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecachefinalize">RxNameCacheFinalize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecachefreeentry">RxNameCacheFreeEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecacheinitialize">RxNameCacheInitialize</a>
 

 

