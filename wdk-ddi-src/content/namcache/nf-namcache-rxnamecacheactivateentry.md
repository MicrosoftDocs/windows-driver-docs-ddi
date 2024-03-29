---
UID: NF:namcache.RxNameCacheActivateEntry
title: RxNameCacheActivateEntry function (namcache.h)
description: RxNameCacheActivateEntry takes a name cache entry and updates the expiration time and the network mini-redirector context. It then puts the name cache entry on the active list.
old-location: ifsk\rxnamecacheactivateentry.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["RxNameCacheActivateEntry function"]
ms.keywords: RxNameCacheActivateEntry, RxNameCacheActivateEntry function [Installable File System Drivers], ifsk.rxnamecacheactivateentry, namcache/RxNameCacheActivateEntry, rxref_f8bd601f-32b7-4164-beb5-c020f3670fe7.xml
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
 - RxNameCacheActivateEntry
 - namcache/RxNameCacheActivateEntry
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - namcache.h
api_name:
 - RxNameCacheActivateEntry
---

# RxNameCacheActivateEntry function


## -description

<b>RxNameCacheActivateEntry</b> takes a name cache entry and updates the expiration time and the network mini-redirector context. It then puts the name cache entry on the active list.

## -parameters

### -param NameCacheCtl [in]


A pointer to the NAME_CACHE_CONTROL structure on which to activate the entry.

### -param NameCache [in]


A pointer to the NAME_CACHE structure to activate.

### -param LifeTime [in]


A value that indicates the valid lifetime in seconds of the cache entry. A value of 0 means to leave the current value unchanged. A value of 0 is used for reactivations after a match where you want the original lifetime preserved.

### -param MRxContext [in]


A value of context supplied by the network mini-redirector for equality checking when making a valid entry check. An <i>MRxContext</i> value of 0 means to leave the current value unchanged. A value of 0 is used for reactivations after a match where you want the original <i>MRxContext</i> preserved.

## -remarks

The <b>RxNameCacheActivateEntry</b> routine is normally called after a network mini-redirector calls <b>RxNameCacheCreateEntry</b> to allocate and initialize a NAME_CACHE structure with the given name string. It is expected that the caller will then initialize any additional network mini-redirector elements of the name cache context, such as <i>Lifetime</i> (in seconds) and <i>MRxContext</i>, and then put the entry on the name cache active list by calling <b>RxNameCacheActivateEntry</b>.

The <b>RxNameCacheActivateEntry</b> routine assumes that the name cache entry is not on either the free or active list.

## -see-also

<a href="/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecachecheckentry">RxNameCacheCheckEntry</a>



<a href="/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecachecreateentry">RxNameCacheCreateEntry</a>



<a href="/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecacheexpireentry">RxNameCacheExpireEntry</a>



<a href="/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecacheexpireentrywithshortname">RxNameCacheExpireEntryWithShortName</a>



<a href="/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecachefetchentry">RxNameCacheFetchEntry</a>



<a href="/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecachefinalize">RxNameCacheFinalize</a>



<a href="/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecachefreeentry">RxNameCacheFreeEntry</a>



<a href="/windows-hardware/drivers/ddi/namcache/nf-namcache-rxnamecacheinitialize">RxNameCacheInitialize</a>
