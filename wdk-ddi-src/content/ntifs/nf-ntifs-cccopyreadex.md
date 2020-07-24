---
UID: NF:ntifs.CcCopyReadEx
title: CcCopyReadEx function (ntifs.h)
description: The CcCopyReadEx routine copies data from a cached file to a user buffer. The I/O byte count for the operation is charged to the issuing thread.
old-location: ifsk\cccopyreadex.htm
tech.root: ifsk
ms.assetid: 4108EB7A-F8FB-4FA5-8426-BB434E89AF06
ms.date: 04/16/2018
keywords: ["CcCopyReadEx function"]
ms.keywords: CcCopyReadEx, CcCopyReadEx routine [Installable File System Drivers], ifsk.cccopyreadex, ntifs/CcCopyReadEx
f1_keywords:
 - "ntifs/CcCopyReadEx"
 - "CcCopyReadEx"
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- CcCopyReadEx
targetos: Windows
req.typenames: 
---

# CcCopyReadEx function


## -description


The <b>CcCopyReadEx</b> routine copies data from a cached file to a user buffer. The I/O byte count for the operation is charged to the issuing thread.


## -parameters




### -param FileObject [in]

A pointer to a file object for the cached file from which the data is to be read.


### -param FileOffset [in]

A pointer to a variable that specifies the starting byte offset within the cached file.


### -param Length [in]

The length in bytes of the data to be read.


### -param Wait [in]

Set to <b>TRUE</b> if the caller can be put into a wait state until all the data has been copied, <b>FALSE</b> otherwise.


### -param Buffer [out]

A pointer to a buffer into which the data is to be copied. 


### -param IoStatus [out]

A pointer to a caller-allocated structure that receives the final completion status and information about the operation. If not all of the data is copied successfully, <i>IoStatus.Information</i> contains the actual number of bytes that were copied.


### -param IoIssuerThread [in]

The thread issuing the read request. For a file system with disk I/O accounting enabled, this is the thread the I/O is charged to. If <i>IoIssuerThread</i> is NULL, the I/O is charged to the current thread.


## -returns



The <b>CcCopyReadEx</b> routine returns <b>TRUE</b> if the data was copied successfully, <b>FALSE</b> otherwise.




## -remarks



If <i>Wait</i> is <b>TRUE</b>, <b>CcCopyReadEx</b> is guaranteed to complete the copy request and return <b>TRUE</b>. If the required pages of the cached file are already resident in memory, the data will be copied immediately and no blocking will occur. If any needed pages are not resident, the caller will be put in a wait state until all required pages have been made resident and the data can be copied.

If <i>Wait</i> is <b>FALSE</b>, <b>CcCopyReadEx</b> will refuse to block, and will return <b>FALSE</b>, if the required pages of the cached file are not already resident in memory. 

<i>FileOffset</i> plus <i>Length</i> must be less than or equal to the size of the cached file, or an assertion failure will occur.

If any failure occurs, <b>CcCopyReadEx</b> raises a status exception for that particular failure. For example, if a pool allocation failure occurs, <b>CcCopyReadEx</b> raises an exception with the <b>STATUS_INSUFFICIENT_RESOURCES</b> status; if an I/O error occurs, <b>CcCopyReadEx</b> raises the status exception of the I/O error. Therefore, to gain control if a failure occurs, the driver should wrap the call to <b>CcCopyReadEx</b> in a <b>try-except</b> or <b>try-finally</b> statement.

To cache a file, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539067">CcFastCopyRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>



<a href="https://docs.microsoft.com/previous-versions/ff539191(v=vs.85)">CcReadAhead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539200">CcScheduleReadAhead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539203">CcSetAdditionalCacheAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539224">CcSetReadAheadGranularity</a>
 

 

