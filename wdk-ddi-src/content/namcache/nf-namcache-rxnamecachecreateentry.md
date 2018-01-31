---
UID: NF:namcache.RxNameCacheCreateEntry
title: RxNameCacheCreateEntry function
author: windows-driver-content
description: RxNameCacheCreateEntry allocates and initializes a NAME_CACHE structure with the given name string.
old-location: ifsk\rxnamecachecreateentry.htm
old-project: ifsk
ms.assetid: 1cfe2d2d-99fa-4dc2-b517-5026fd72d5d4
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: rxref_a1245999-8aba-4012-a143-609517c2686b.xml, namcache/RxNameCacheCreateEntry, RxNameCacheCreateEntry, ifsk.rxnamecachecreateentry, RxNameCacheCreateEntry function [Installable File System Drivers]
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	namcache.h
apiname:
-	RxNameCacheCreateEntry
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# RxNameCacheCreateEntry function


## -description


<b>RxNameCacheCreateEntry</b> allocates and initializes a NAME_CACHE structure with the given name string. 


## -syntax


````
PNAME_CACHE RxNameCacheCreateEntry(
  _In_ PNAME_CACHE_CONTROL NameCacheCtl,
  _In_ PUNICODE_STRING     Name,
  _In_ BOOLEAN             CaseInsensitive
);
````


## -parameters




#### - NameCacheCtl [in]

A pointer to the NAME_CACHE_CONTROL structure from which to allocate the entry.


#### - Name [in]

A pointer to the Unicode name string with which to initialize the name cache entry.


#### - CaseInsensitive [in]

A Boolean value that indicates if case insensitive comparions should be used when comparing the <i>Name</i> parameter. 


## -returns


<b>RxNameCacheCreateEntry </b>returns a pointer to the newly allocated NAME_CACHE structure on success or a <b>NULL</b> pointer if the allocation fails.



## -remarks


A network mini-redirector calls <b>RxNameCacheCreateEntry</b> to allocate and initialize a NAME_CACHE structure with the given name string. It is expected that the caller will then initialize any additional network mini-redirector elements of the name cache context, set the lifetime (in seconds) and the <b>Context</b> member of the NAME_CACHE structure and then put the entry on the name cache active list by calling <b>RxNameCacheActivateEntry</b>.

<b>RxNameCacheCreateEntry</b> will first attempt to reuse a NAME_CACHE entry on the free list, if one is available, before allocating a new NAME_CACHE entry. 



## -see-also

<a href="..\namcache\nf-namcache-rxnamecachefinalize.md">RxNameCacheFinalize</a>

<a href="..\namcache\nf-namcache-rxnamecachecheckentry.md">RxNameCacheCheckEntry</a>

<a href="..\namcache\nf-namcache-rxnamecacheinitialize.md">RxNameCacheInitialize</a>

<a href="..\namcache\nf-namcache-rxnamecacheexpireentry.md">RxNameCacheExpireEntry</a>

<a href="..\namcache\nf-namcache-rxnamecacheexpireentrywithshortname.md">RxNameCacheExpireEntryWithShortName</a>

<a href="..\namcache\nf-namcache-rxnamecachefetchentry.md">RxNameCacheFetchEntry</a>

<a href="..\namcache\nf-namcache-rxnamecachefreeentry.md">RxNameCacheFreeEntry</a>

<a href="..\namcache\nf-namcache-rxnamecacheactivateentry.md">RxNameCacheActivateEntry</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxNameCacheCreateEntry function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

