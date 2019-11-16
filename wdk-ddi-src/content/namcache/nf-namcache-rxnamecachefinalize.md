---
UID: NF:namcache.RxNameCacheFinalize
title: RxNameCacheFinalize function (namcache.h)
description: RxNameCacheFinalize releases the storage for all of the NAME_CACHE entries associated with a NAME_CACHE_CONTROL structure.
old-location: ifsk\rxnamecachefinalize.htm
tech.root: ifsk
ms.assetid: e40ac123-86a9-4a69-bb13-a118f2fd42f1
ms.date: 04/16/2018
ms.keywords: RxNameCacheFinalize, RxNameCacheFinalize function [Installable File System Drivers], ifsk.rxnamecachefinalize, namcache/RxNameCacheFinalize, rxref_34ec3c3b-20b2-425a-8d12-4a2d685ffb2f.xml
ms.topic: function
f1_keywords:
 - "namcache/RxNameCacheFinalize"
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
- RxNameCacheFinalize
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxNameCacheFinalize function


## -description


<b>RxNameCacheFinalize</b> releases the storage for all of the NAME_CACHE entries associated with a NAME_CACHE_CONTROL structure.


## -parameters




### -param NameCacheCtl [in]

A pointer to the NAME_CACHE_CONTROL structure for the name cache.


## -remarks



The <b>RxNameCacheFinalize </b>routine acquires the lock on the name cache to scan the free list and remove entries from the active list. 

On checked builds, this routine causes the system to ASSERT if after releasing all of the active and free entries a reference count still remains on the name cache. This indicates a memory leak where some caller did not call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecachefreeentry">RxNameCacheFreeEntry</a> when done with an entry.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecacheactivateentry">RxNameCacheActivateEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecachecheckentry">RxNameCacheCheckEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecachecreateentry">RxNameCacheCreateEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecacheexpireentry">RxNameCacheExpireEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecacheexpireentrywithshortname">RxNameCacheExpireEntryWithShortName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecachefetchentry">RxNameCacheFetchEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecachefreeentry">RxNameCacheFreeEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecacheinitialize">RxNameCacheInitialize</a>
 

 

