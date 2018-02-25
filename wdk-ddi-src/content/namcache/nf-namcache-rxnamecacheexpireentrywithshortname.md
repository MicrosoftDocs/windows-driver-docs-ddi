---
UID: NF:namcache.RxNameCacheExpireEntryWithShortName
title: RxNameCacheExpireEntryWithShortName function
author: windows-driver-content
description: RxNameCacheExpireEntryWithShortName expires all of the name cache entries whose name prefix matches the given short file name.
old-location: ifsk\rxnamecacheexpireentrywithshortname.htm
old-project: ifsk
ms.assetid: 4d842454-4a59-4f82-9aeb-3dfbe9d8cd8a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , C, E, N, R, RxNameCacheExpireEntryWithShortName, RxNameCacheExpireEntryWithShortName function [Installable File System Drivers], S, W, a, c, e, h, i, ifsk.rxnamecacheexpireentrywithshortname, m, n, namcache/RxNameCacheExpireEntryWithShortName, o, p, r, rxref_fcde2e61-9855-4d66-8b81-a437921d5ec5.xml, t, x, y"
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
-	RxNameCacheExpireEntryWithShortName
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# RxNameCacheExpireEntryWithShortName function


## -description


<b>RxNameCacheExpireEntryWithShortName</b> expires all of the name cache entries whose name prefix matches the given short file name.


## -syntax


````
VOID RxNameCacheExpireEntryWithShortName(
  _In_ PNAME_CACHE_CONTROL NameCacheCtl,
  _In_ PUNICODE_STRING     Name
);
````


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

<a href="..\namcache\nf-namcache-rxnamecacheinitialize.md">RxNameCacheInitialize</a>



<a href="..\namcache\nf-namcache-rxnamecachefreeentry.md">RxNameCacheFreeEntry</a>



<a href="..\namcache\nf-namcache-rxnamecacheactivateentry.md">RxNameCacheActivateEntry</a>



<a href="..\namcache\nf-namcache-rxnamecachefetchentry.md">RxNameCacheFetchEntry</a>



<a href="..\namcache\nf-namcache-rxnamecachefinalize.md">RxNameCacheFinalize</a>



<a href="..\namcache\nf-namcache-rxnamecacheexpireentry.md">RxNameCacheExpireEntry</a>



<a href="..\namcache\nf-namcache-rxnamecachecheckentry.md">RxNameCacheCheckEntry</a>



<a href="..\namcache\nf-namcache-rxnamecachecreateentry.md">RxNameCacheCreateEntry</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxNameCacheExpireEntryWithShortName function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

