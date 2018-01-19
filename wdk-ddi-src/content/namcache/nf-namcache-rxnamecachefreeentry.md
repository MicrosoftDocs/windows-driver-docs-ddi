---
UID: NF:namcache.RxNameCacheFreeEntry
title: RxNameCacheFreeEntry function
author: windows-driver-content
description: RxNameCacheFreeEntry releases the storage for a NAME_CACHE entry and decrements the count of the NAME_CACHE cache entries associated with a NAME_CACHE_CONTROL structure.
old-location: ifsk\rxnamecachefreeentry.htm
old-project: ifsk
ms.assetid: c1adef80-b8f2-49bb-9254-b89c8d1af220
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RxNameCacheFreeEntry
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
req.alt-api: RxNameCacheFreeEntry
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

# RxNameCacheFreeEntry function



## -description
<b>RxNameCacheFreeEntry</b> releases the storage for a NAME_CACHE entry and decrements the count of the NAME_CACHE cache entries associated with a NAME_CACHE_CONTROL structure. 



## -syntax

````
VOID RxNameCacheFreeEntry(
  _In_ PNAME_CACHE_CONTROL NameCacheCtl,
  _In_ PNAME_CACHE         NameCache
);
````


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
<a href="..\namcache\nf-namcache-rxnamecacheexpireentry.md">RxNameCacheExpireEntry</a>
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
<a href="..\namcache\nf-namcache-rxnamecacheinitialize.md">RxNameCacheInitialize</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxNameCacheFreeEntry function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

