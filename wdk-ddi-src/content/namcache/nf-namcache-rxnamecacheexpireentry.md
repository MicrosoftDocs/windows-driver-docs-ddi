---
UID: NF:namcache.RxNameCacheExpireEntry
title: RxNameCacheExpireEntry function
author: windows-driver-content
description: RxNameCacheExpireEntry puts a NAME_CACHE entry on the free list for recycling.
old-location: ifsk\rxnamecacheexpireentry.htm
old-project: ifsk
ms.assetid: cd763f88-0ff6-4938-ac6e-88ed3da2022b
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RxNameCacheExpireEntry
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
req.alt-api: RxNameCacheExpireEntry
req.alt-loc: namcache.h
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
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# RxNameCacheExpireEntry function



## -description
<b>RxNameCacheExpireEntry</b> puts a NAME_CACHE entry on the free list for recycling.



## -syntax

````
VOID RxNameCacheExpireEntry(
  _In_ PNAME_CACHE_CONTROL NameCacheCtl,
  _In_ PNAME_CACHE         NameCache
);
````


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
<dl>
<dt>
<a href="..\namcache\nf-namcache-rxnamecacheactivateentry.md">RxNameCacheActivateEntry</a>
</dt>
<dt>
<a href="..\namcache\nf-namcache-rxnamecachecheckentry.md">RxNameCacheCheckEntry</a>
</dt>
<dt>
<a href="..\namcache\nf-namcache-rxnamecachecreateentry.md">RxNameCacheCreateEntry</a>
</dt>
<dt>
<a href="..\namcache\nf-namcache-rxnamecacheexpireentrywithshortname.md">RxNameCacheExpireEntryWithShortName</a>
</dt>
<dt>
<a href="..\namcache\nf-namcache-rxnamecachefetchentry.md">RxNameCacheFetchEntry</a>
</dt>
<dt>
<a href="..\namcache\nf-namcache-rxnamecachefinalize.md">RxNameCacheFinalize</a>
</dt>
<dt>
<a href="..\namcache\nf-namcache-rxnamecachefreeentry.md">RxNameCacheFreeEntry</a>
</dt>
<dt>
<a href="..\namcache\nf-namcache-rxnamecacheinitialize.md">RxNameCacheInitialize</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxNameCacheExpireEntry function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

