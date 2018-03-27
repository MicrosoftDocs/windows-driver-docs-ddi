---
UID: NF:ntifs.CcCanIWrite
title: CcCanIWrite function
author: windows-driver-content
description: The CcCanIWrite routine determines whether the caller can write to a cached file.
old-location: ifsk\cccaniwrite.htm
old-project: ifsk
ms.assetid: 04b1521f-906f-493d-9ca6-6d97c6a80bdb
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: CcCanIWrite, CcCanIWrite routine [Installable File System Drivers], ccref_b964dbf1-d1ad-4929-ab9c-21b1e6f69077.xml, ifsk.cccaniwrite, ntifs/CcCanIWrite
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
-	CcCanIWrite
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# CcCanIWrite function


## -description


The <b>CcCanIWrite</b> routine determines whether the caller can write to a cached file.


## -parameters




### -param FileObject [in]

Pointer to a file object for the cached file.


### -param BytesToWrite [in]

Number of bytes to be written.


### -param Wait [in]

Set to <b>TRUE</b> if the caller can be put into a wait state until it can write to the cached file, <b>FALSE</b> otherwise.


### -param Retrying [in]

Set to <b>FALSE</b> if this is the first time <b>CcCanIWrite</b> is being called for this write request, <b>TRUE</b> otherwise.


## -returns



<b>CcCanIWrite</b> returns <b>TRUE</b> if the cache manager can accept the write request, <b>FALSE</b> otherwise.




## -remarks



<b>CcCanIWrite</b> should be called before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff539045">CcCopyWrite</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff539075">CcFastCopyWrite</a>.

If <b>CcCanIWrite</b> returns <b>TRUE</b>, the caller can immediately call <a href="https://msdn.microsoft.com/library/windows/hardware/ff539045">CcCopyWrite</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff539075">CcFastCopyWrite</a>.

If <b>CcCanIWrite</b> returns <b>FALSE</b>, the caller must instead call <a href="https://msdn.microsoft.com/library/windows/hardware/ff539060">CcDeferWrite</a> to defer the write request.

Generally speaking, the cache manager can accept a write request if the following conditions are true:

<ul>
<li>
The amount of data to be written is not too large.

</li>
<li>
There is enough memory to perform the write operation.

</li>
<li>
The number of dirty pages in the system cache does not exceed the dirty page threshold (CcDirtyPageThreshold).

</li>
<li>
If a per-file dirty page threshold exists for this file, it is not exceeded by the number of dirty pages for this file in the system cache.

</li>
</ul>
To cache a file, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539045">CcCopyWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539060">CcDeferWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539075">CcFastCopyWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539209">CcSetDirtyPageThreshold</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcCanIWrite routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

