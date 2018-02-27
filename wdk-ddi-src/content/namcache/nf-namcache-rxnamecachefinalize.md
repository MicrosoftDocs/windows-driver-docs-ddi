---
UID: NF:namcache.RxNameCacheFinalize
title: RxNameCacheFinalize function
author: windows-driver-content
description: RxNameCacheFinalize releases the storage for all of the NAME_CACHE entries associated with a NAME_CACHE_CONTROL structure.
old-location: ifsk\rxnamecachefinalize.htm
old-project: ifsk
ms.assetid: e40ac123-86a9-4a69-bb13-a118f2fd42f1
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxNameCacheFinalize, RxNameCacheFinalize function [Installable File System Drivers], ifsk.rxnamecachefinalize, namcache/RxNameCacheFinalize, rxref_34ec3c3b-20b2-425a-8d12-4a2d685ffb2f.xml
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
-	RxNameCacheFinalize
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# RxNameCacheFinalize function


## -description


<b>RxNameCacheFinalize</b> releases the storage for all of the NAME_CACHE entries associated with a NAME_CACHE_CONTROL structure.


## -syntax


````
VOID RxNameCacheFinalize(
  _In_ PNAME_CACHE_CONTROL NameCacheCtl
);
````


## -parameters




### -param NameCacheCtl [in]

A pointer to the NAME_CACHE_CONTROL structure for the name cache.


## -returns



None




## -remarks



The <b>RxNameCacheFinalize </b>routine acquires the lock on the name cache to scan the free list and remove entries from the active list. 

On checked builds, this routine causes the system to ASSERT if after releasing all of the active and free entries a reference count still remains on the name cache. This indicates a memory leak where some caller did not call <a href="..\namcache\nf-namcache-rxnamecachefreeentry.md">RxNameCacheFreeEntry</a> when done with an entry.




## -see-also

<a href="..\namcache\nf-namcache-rxnamecachecreateentry.md">RxNameCacheCreateEntry</a>



<a href="..\namcache\nf-namcache-rxnamecachefetchentry.md">RxNameCacheFetchEntry</a>



<a href="..\namcache\nf-namcache-rxnamecacheexpireentry.md">RxNameCacheExpireEntry</a>



<a href="..\namcache\nf-namcache-rxnamecacheexpireentrywithshortname.md">RxNameCacheExpireEntryWithShortName</a>



<a href="..\namcache\nf-namcache-rxnamecacheactivateentry.md">RxNameCacheActivateEntry</a>



<a href="..\namcache\nf-namcache-rxnamecachecheckentry.md">RxNameCacheCheckEntry</a>



<a href="..\namcache\nf-namcache-rxnamecachefreeentry.md">RxNameCacheFreeEntry</a>



<a href="..\namcache\nf-namcache-rxnamecacheinitialize.md">RxNameCacheInitialize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxNameCacheFinalize function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

