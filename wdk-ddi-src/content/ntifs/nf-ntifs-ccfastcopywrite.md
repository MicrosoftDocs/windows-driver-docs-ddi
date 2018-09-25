---
UID: NF:ntifs.CcFastCopyWrite
title: CcFastCopyWrite function
author: windows-driver-content
description: The CcFastCopyWrite routine performs a fast copy write from a buffer in memory to a cached file.
old-location: ifsk\ccfastcopywrite.htm
tech.root: ifsk
ms.assetid: 414d0b36-d7c2-4a01-8ceb-3817a11c422c
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: CcFastCopyWrite, CcFastCopyWrite routine [Installable File System Drivers], ccref_f5763242-c6f6-4638-8577-a6c65001a8ca.xml, ifsk.ccfastcopywrite, ntifs/CcFastCopyWrite
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
-	CcFastCopyWrite
product:
- Windows
targetos: Windows
req.typenames: 
---

# CcFastCopyWrite function


## -description


The <b>CcFastCopyWrite</b> routine performs a fast copy write from a buffer in memory to a cached file.


## -parameters




### -param FileObject [in]

Pointer to a file object for the cached file to which the data is to be written.


### -param FileOffset [in]

Pointer to a variable that specifies the starting byte offset within the cached file.


### -param Length [in]

Length in bytes of the data to be written.


### -param Buffer [in]

Pointer to the buffer from which the data is to be copied.


## -returns



None




## -remarks



<b>CcFastCopyWrite</b> is a faster version of <a href="https://msdn.microsoft.com/library/windows/hardware/ff539045">CcCopyWrite</a>. It differs from <b>CcCopyWrite</b> in the following respects:

<ul>
<li>
<i>FileOffset</i> is a ULONG, not a PLARGE_INTEGER.

</li>
<li>
There is no <i>Wait</i> parameter. The caller must be able to enter a wait state until all the data has been copied.

</li>
<li>
<b>CcFastCopyWrite</b> does not return a BOOLEAN to indicate whether the write operation was successful.

</li>
</ul>
If the required pages of the cached file are already resident in memory, the data is copied immediately and no blocking occurs. If any needed pages are not resident, the caller is put in a wait state until all required pages have been made resident and the data can be copied.

If any failure occurs, <b>CcFastCopyWrite</b> raises a status exception for that particular failure. For example, if a pool allocation failure occurs, <b>CcFastCopyWrite</b> raises a STATUS_INSUFFICIENT_RESOURCES exception; if an I/O error occurs, <b>CcFastCopyWrite</b> raises the status exception of the I/O error. Therefore, to gain control if a failure occurs, the driver should wrap the call to <b>CcFastCopyWrite</b> in a <b>try-except</b> or <b>try-finally</b> statement.

To cache a file, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539045">CcCopyWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>
 

 

