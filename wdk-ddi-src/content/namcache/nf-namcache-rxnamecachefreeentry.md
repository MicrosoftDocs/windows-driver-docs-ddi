---
UID: NF:namcache.RxNameCacheFreeEntry
title: RxNameCacheFreeEntry function (namcache.h)
description: RxNameCacheFreeEntry releases the storage for a NAME_CACHE entry and decrements the count of the NAME_CACHE cache entries associated with a NAME_CACHE_CONTROL structure.
old-location: ifsk\rxnamecachefreeentry.htm
tech.root: ifsk
ms.assetid: c1adef80-b8f2-49bb-9254-b89c8d1af220
ms.date: 04/16/2018
keywords: ["RxNameCacheFreeEntry function"]
ms.keywords: RxNameCacheFreeEntry, RxNameCacheFreeEntry function [Installable File System Drivers], ifsk.rxnamecachefreeentry, namcache/RxNameCacheFreeEntry, rxref_ca0b7c99-59df-4a51-b28b-4c369b451741.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RxNameCacheFreeEntry
 - namcache/RxNameCacheFreeEntry
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - namcache.h
api_name:
 - RxNameCacheFreeEntry
---

# RxNameCacheFreeEntry function


## -description

<b>RxNameCacheFreeEntry</b> releases the storage for a NAME_CACHE entry and decrements the count of the NAME_CACHE cache entries associated with a NAME_CACHE_CONTROL structure.

## -parameters

### -param NameCacheCtl 

[in]
A pointer to the NAME_CACHE_CONTROL structure for the name cache.

### -param NameCache 

[in]
A pointer to the NAME_CACHE structure to free.

## -remarks

The <b>RxNameCacheFreeEntry</b> routine assumes that the name cache entry is not on either the free or active list.

The <b>RxNameCacheFreeEntry</b> routine frees memory allocated for the name buffer if the name buffer for this name cache entry is not <b>NULL</b>. This routine will then free memory used for the NAME_CACHE entry. Then, the count of name cache entries on <i>NameCacheCtl</i> is decremented.

## -see-also

<a href="/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecacheactivateentry">RxNameCacheActivateEntry</a>



<a href="/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecachecheckentry">RxNameCacheCheckEntry</a>



<a href="/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecachecreateentry">RxNameCacheCreateEntry</a>



<a href="/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecacheexpireentry">RxNameCacheExpireEntry</a>



<a href="/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecacheexpireentrywithshortname">RxNameCacheExpireEntryWithShortName</a>



<a href="/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecachefetchentry">RxNameCacheFetchEntry</a>



<a href="/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecachefinalize">RxNameCacheFinalize</a>



<a href="/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecacheinitialize">RxNameCacheInitialize</a>