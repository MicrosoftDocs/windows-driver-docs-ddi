---
UID: NF:namcache.RxNameCacheInitialize
title: RxNameCacheInitialize function
author: windows-driver-content
description: RxNameCacheInitialize initializes a name cache (NAME_CACHE_CONTROL structure).
old-location: ifsk\rxnamecacheinitialize.htm
old-project: ifsk
ms.assetid: 2a124a6e-30ff-4c0d-9a09-8cf43e65a657
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: RxNameCacheInitialize, RxNameCacheInitialize function [Installable File System Drivers], ifsk.rxnamecacheinitialize, namcache/RxNameCacheInitialize, rxref_1a97be61-3797-49f0-ad90-e426e43505c1.xml
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
req.lib: 
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	namcache.h
api_name:
-	RxNameCacheInitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxNameCacheInitialize function


## -description


<b>RxNameCacheInitialize</b> initializes a name cache (NAME_CACHE_CONTROL structure).


## -parameters




### -param NameCacheCtl [in]

A pointer to the NAME_CACHE_CONTROL structure to initialize.


### -param MRxNameCacheSize [in]

The size, in bytes, of the network mini-redirector portion of the NAME_CACHE entry.


### -param MaximumEntries [in]

The maximum number of entries that will ever be allocated. This value prevents an errant program that opens a large number of files with bad names from using all of the paged pool memory.


## -returns



None




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554552">RxNameCacheActivateEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554558">RxNameCacheCheckEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554565">RxNameCacheCreateEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554569">RxNameCacheExpireEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554570">RxNameCacheExpireEntryWithShortName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554573">RxNameCacheFetchEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554575">RxNameCacheFinalize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554579">RxNameCacheFreeEntry</a>
 

 

