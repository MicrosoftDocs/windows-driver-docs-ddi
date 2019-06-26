---
UID: NF:namcache.RxNameCacheExpireEntry
title: RxNameCacheExpireEntry function (namcache.h)
description: RxNameCacheExpireEntry puts a NAME_CACHE entry on the free list for recycling.
old-location: ifsk\rxnamecacheexpireentry.htm
tech.root: ifsk
ms.assetid: cd763f88-0ff6-4938-ac6e-88ed3da2022b
ms.date: 04/16/2018
ms.keywords: RxNameCacheExpireEntry, RxNameCacheExpireEntry function [Installable File System Drivers], ifsk.rxnamecacheexpireentry, namcache/RxNameCacheExpireEntry, rxref_d516a8aa-e7f8-48d4-8619-6b59a862ca0c.xml
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
- RxNameCacheExpireEntry
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxNameCacheExpireEntry function


## -description


<b>RxNameCacheExpireEntry</b> puts a NAME_CACHE entry on the free list for recycling.


## -parameters




### -param NameCacheCtl [in]

A pointer to the NAME_CACHE_CONTROL structure on which to expire the entry.


### -param NameCache [in]

A pointer to the NAME_CACHE structure to expire.


## -returns



None




## -remarks



The <b>RxNameCacheExpireEntry</b> routine assumes that the name cache entry is not on the active or free list. This routine inserts the <i>NameCache</i> entry at the head of the free list and subtracts one from the <b>NumberActivates</b> member of the NAME_CACHE_CONTROL structure pointed to by <i>NameCacheCtl</i> to update statistics.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/namcache/nf-namcache-rxnamecacheactivateentry">RxNameCacheActivateEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/namcache/nf-namcache-rxnamecachecheckentry">RxNameCacheCheckEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/namcache/nf-namcache-rxnamecachecreateentry">RxNameCacheCreateEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/namcache/nf-namcache-rxnamecacheexpireentrywithshortname">RxNameCacheExpireEntryWithShortName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/namcache/nf-namcache-rxnamecachefetchentry">RxNameCacheFetchEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/namcache/nf-namcache-rxnamecachefinalize">RxNameCacheFinalize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/namcache/nf-namcache-rxnamecachefreeentry">RxNameCacheFreeEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/namcache/nf-namcache-rxnamecacheinitialize">RxNameCacheInitialize</a>
 

 

