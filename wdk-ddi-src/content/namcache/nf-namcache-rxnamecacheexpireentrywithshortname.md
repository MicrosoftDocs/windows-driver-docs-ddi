---
UID: NF:namcache.RxNameCacheExpireEntryWithShortName
title: RxNameCacheExpireEntryWithShortName function (namcache.h)
description: RxNameCacheExpireEntryWithShortName expires all of the name cache entries whose name prefix matches the given short file name.
old-location: ifsk\rxnamecacheexpireentrywithshortname.htm
tech.root: ifsk
ms.assetid: 4d842454-4a59-4f82-9aeb-3dfbe9d8cd8a
ms.date: 04/16/2018
ms.keywords: RxNameCacheExpireEntryWithShortName, RxNameCacheExpireEntryWithShortName function [Installable File System Drivers], ifsk.rxnamecacheexpireentrywithshortname, namcache/RxNameCacheExpireEntryWithShortName, rxref_fcde2e61-9855-4d66-8b81-a437921d5ec5.xml
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- namcache.h
api_name:
- RxNameCacheExpireEntryWithShortName
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxNameCacheExpireEntryWithShortName function


## -description


<b>RxNameCacheExpireEntryWithShortName</b> expires all of the name cache entries whose name prefix matches the given short file name.


## -parameters




### -param NameCacheCtl [in]

A pointer to the NAME_CACHE_CONTROL structure to scan.


### -param Name [in]

A pointer to the Unicode string that contains the name prefix to scan for name cache entry matches to expire.


## -returns



None




## -remarks



The <b>RxNameCacheExpireEntryWithShortName</b> routine scans the active list and inserts any matching NAME_CACHE entries at the head of the free list. The <b>CaseInsensitive</b> member of the NAME_CACHE entry is used to determine whether the scan should ignore case sensitivity when matching the <i>Name</i> parameter.

Because the active list is scanned, the <b>RxNameCacheExpireEntryWithShortName</b> routine puts any non-matching entries that have expired on the free list. A <i>Name</i> value of zero length will match all entries and insert the entries on the free list.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/namcache/nf-namcache-rxnamecacheactivateentry">RxNameCacheActivateEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/namcache/nf-namcache-rxnamecachecheckentry">RxNameCacheCheckEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/namcache/nf-namcache-rxnamecachecreateentry">RxNameCacheCreateEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/namcache/nf-namcache-rxnamecacheexpireentry">RxNameCacheExpireEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/namcache/nf-namcache-rxnamecachefetchentry">RxNameCacheFetchEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/namcache/nf-namcache-rxnamecachefinalize">RxNameCacheFinalize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/namcache/nf-namcache-rxnamecachefreeentry">RxNameCacheFreeEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/namcache/nf-namcache-rxnamecacheinitialize">RxNameCacheInitialize</a>
 

 

