---
UID: NF:ntifs.CcSetDirtyPageThreshold
title: CcSetDirtyPageThreshold function
author: windows-driver-content
description: The CcSetDirtyPageThreshold routine sets a per-file dirty page threshold on a cached file.
old-location: ifsk\ccsetdirtypagethreshold.htm
old-project: ifsk
ms.assetid: ba7023d9-5130-4eea-9de9-034f5bf0b145
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: CcSetDirtyPageThreshold, CcSetDirtyPageThreshold routine [Installable File System Drivers], ccref_df331e54-32a2-4a09-a1e6-7c1d69b2abcf.xml, ifsk.ccsetdirtypagethreshold, ntifs/CcSetDirtyPageThreshold
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
-	CcSetDirtyPageThreshold
product: Windows
targetos: Windows
req.typenames: 
---

# CcSetDirtyPageThreshold function


## -description


The <b>CcSetDirtyPageThreshold</b> routine sets a per-file dirty page threshold on a cached file.


## -parameters




### -param FileObject [in]

Pointer to a file object for the cached file on which the dirty page threshold is to be set.


### -param DirtyPageThreshold [in]

Specifies, as a number of pages, the dirty page threshold value. To remove a per-file dirty page threshold value that was set previously, set <i>DirtyPageThreshold</i> to zero.


## -returns



None




## -remarks



<b>CcSetDirtyPageThreshold</b> sets or removes a per-file dirty page threshold. After a per-file dirty page threshold is set on a cached file, if the file system attempts to exceed the threshold, the cache manager will refuse requests to write to the file.

To determine whether the cache manager will accept or refuse write requests, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff539021">CcCanIWrite</a>.

Note that the <i>per-file</i> dirty page threshold is not the same as the <i>global</i> dirty page threshold for the entire system cache.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539021">CcCanIWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539060">CcDeferWrite</a>
 

 

