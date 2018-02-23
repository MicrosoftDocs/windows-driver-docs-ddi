---
UID: NF:namcache.RxNameCacheActivateEntry
title: RxNameCacheActivateEntry function
author: windows-driver-content
description: RxNameCacheActivateEntry takes a name cache entry and updates the expiration time and the network mini-redirector context. It then puts the name cache entry on the active list.
old-location: ifsk\rxnamecacheactivateentry.htm
old-project: ifsk
ms.assetid: 6ebd4b00-ec25-4383-beba-0478b3241f09
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: rxref_f8bd601f-32b7-4164-beb5-c020f3670fe7.xml, namcache/RxNameCacheActivateEntry, ifsk.rxnamecacheactivateentry, RxNameCacheActivateEntry function [Installable File System Drivers], RxNameCacheActivateEntry
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
-	RxNameCacheActivateEntry
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# RxNameCacheActivateEntry function


## -description


<b>RxNameCacheActivateEntry</b> takes a name cache entry and updates the expiration time and the network mini-redirector context. It then puts the name cache entry on the active list.


## -syntax


````
VOID RxNameCacheActivateEntry(
  _In_ PNAME_CACHE_CONTROL NameCacheCtl,
  _In_ PNAME_CACHE         NameCache,
  _In_ ULONG               LifeTime,
  _In_ ULONG               MRxContext
);
````


## -parameters




### -param NameCacheCtl [in]

A pointer to the NAME_CACHE_CONTROL structure on which to activate the entry.


### -param NameCache [in]

A pointer to the NAME_CACHE structure to activate.


### -param LifeTime [in]

A value that indicates the valid lifetime in seconds of the cache entry. A value of 0 means to leave the current value unchanged. A value of 0 is used for reactivations after a match where you want the original lifetime preserved.


### -param MRxContext [in]

A value of context supplied by the network mini-redirector for equality checking when making a valid entry check. An <i>MRxContext</i> value of 0 means to leave the current value unchanged. A value of 0 is used for reactivations after a match where you want the original <i>MRxContext</i> preserved.


## -returns



None




## -remarks



The <b>RxNameCacheActivateEntry</b> routine is normally called after a network mini-redirector calls <b>RxNameCacheCreateEntry</b> to allocate and initialize a NAME_CACHE structure with the given name string. It is expected that the caller will then initialize any additional network mini-redirector elements of the name cache context, such as <i>Lifetime</i> (in seconds) and <i>MRxContext</i>, and then put the entry on the name cache active list by calling <b>RxNameCacheActivateEntry</b>.

The <b>RxNameCacheActivateEntry</b> routine assumes that the name cache entry is not on either the free or active list. 




## -see-also

<a href="..\namcache\nf-namcache-rxnamecachecreateentry.md">RxNameCacheCreateEntry</a>



<a href="..\namcache\nf-namcache-rxnamecacheinitialize.md">RxNameCacheInitialize</a>



<a href="..\namcache\nf-namcache-rxnamecachefreeentry.md">RxNameCacheFreeEntry</a>



<a href="..\namcache\nf-namcache-rxnamecacheexpireentrywithshortname.md">RxNameCacheExpireEntryWithShortName</a>



<a href="..\namcache\nf-namcache-rxnamecachefetchentry.md">RxNameCacheFetchEntry</a>



<a href="..\namcache\nf-namcache-rxnamecachecheckentry.md">RxNameCacheCheckEntry</a>



<a href="..\namcache\nf-namcache-rxnamecacheexpireentry.md">RxNameCacheExpireEntry</a>



<a href="..\namcache\nf-namcache-rxnamecachefinalize.md">RxNameCacheFinalize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxNameCacheActivateEntry function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

