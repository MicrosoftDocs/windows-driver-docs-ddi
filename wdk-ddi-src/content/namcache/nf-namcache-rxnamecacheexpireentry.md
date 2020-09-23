---
UID: NF:namcache.RxNameCacheExpireEntry
title: RxNameCacheExpireEntry function (namcache.h)
description: RxNameCacheExpireEntry puts a NAME_CACHE entry on the free list for recycling.
old-location: ifsk\rxnamecacheexpireentry.htm
tech.root: ifsk
ms.assetid: cd763f88-0ff6-4938-ac6e-88ed3da2022b
ms.date: 04/16/2018
keywords: ["RxNameCacheExpireEntry function"]
ms.keywords: RxNameCacheExpireEntry, RxNameCacheExpireEntry function [Installable File System Drivers], ifsk.rxnamecacheexpireentry, namcache/RxNameCacheExpireEntry, rxref_d516a8aa-e7f8-48d4-8619-6b59a862ca0c.xml
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
 - RxNameCacheExpireEntry
 - namcache/RxNameCacheExpireEntry
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - namcache.h
api_name:
 - RxNameCacheExpireEntry
---

# RxNameCacheExpireEntry function


## -description

<b>RxNameCacheExpireEntry</b> puts a NAME_CACHE entry on the free list for recycling.

## -parameters

### -param NameCacheCtl 

[in]
A pointer to the NAME_CACHE_CONTROL structure on which to expire the entry.

### -param NameCache 

[in]
A pointer to the NAME_CACHE structure to expire.

## -remarks

The <b>RxNameCacheExpireEntry</b> routine assumes that the name cache entry is not on the active or free list. This routine inserts the <i>NameCache</i> entry at the head of the free list and subtracts one from the <b>NumberActivates</b> member of the NAME_CACHE_CONTROL structure pointed to by <i>NameCacheCtl</i> to update statistics.

## -see-also

<a href="/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecacheactivateentry">RxNameCacheActivateEntry</a>



<a href="/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecachecheckentry">RxNameCacheCheckEntry</a>



<a href="/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecachecreateentry">RxNameCacheCreateEntry</a>



<a href="/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecacheexpireentrywithshortname">RxNameCacheExpireEntryWithShortName</a>



<a href="/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecachefetchentry">RxNameCacheFetchEntry</a>



<a href="/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecachefinalize">RxNameCacheFinalize</a>



<a href="/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecachefreeentry">RxNameCacheFreeEntry</a>



<a href="/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecacheinitialize">RxNameCacheInitialize</a>