---
UID: NF:ntifs.CcUninitializeCacheMap
title: CcUninitializeCacheMap function
author: windows-driver-content
description: The CcUninitializeCacheMap routine stops the caching of a cached file.
old-location: ifsk\ccuninitializecachemap.htm
tech.root: ifsk
ms.assetid: 00e5abd6-c2d7-4408-aaf4-27a67dd3ee51
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: CcUninitializeCacheMap, CcUninitializeCacheMap routine [Installable File System Drivers], ccref_737f8e52-0bb4-4dfd-8516-16de77410b9a.xml, ifsk.ccuninitializecachemap, ntifs/CcUninitializeCacheMap
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	CcUninitializeCacheMap
product:
- Windows
targetos: Windows
req.typenames: 
---

# CcUninitializeCacheMap function


## -description


The <b>CcUninitializeCacheMap</b> routine stops the caching of a cached file.


## -parameters




### -param FileObject [in]

Pointer to a file object for the cached file.


### -param TruncateSize [in, optional]

If specified, the file was truncated to the specified size, and the cache should be purged accordingly.


### -param UninitializeEvent

TBD




#### - UninitializeCompleteEvent [in, optional]

If specified, the provided event is set to the signaled state when the cached file data has been flushed to disk.


## -returns



<b>CcUninitializeCacheMap</b> returns <b>TRUE</b> if caching was stopped successfully, <b>FALSE</b> otherwise.




## -remarks



All file systems that support file caching must call <b>CcUninitializeCacheMap</b> when closing a file, whether the file is cached or not. Even if the file was created with caching disabled, the file system still must call <b>CcUninitializeCacheMap</b>.

To cache a file, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539188">CcPurgeCacheSection</a>
 

 

