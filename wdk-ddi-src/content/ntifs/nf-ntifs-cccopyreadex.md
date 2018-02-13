---
UID: NF:ntifs.CcCopyReadEx
title: CcCopyReadEx function
author: windows-driver-content
description: The CcCopyReadEx routine copies data from a cached file to a user buffer. The I/O byte count for the operation is charged to the issuing thread.
old-location: ifsk\cccopyreadex.htm
old-project: ifsk
ms.assetid: 4108EB7A-F8FB-4FA5-8426-BB434E89AF06
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: CcCopyReadEx routine [Installable File System Drivers], ifsk.cccopyreadex, ntifs/CcCopyReadEx, CcCopyReadEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	CcCopyReadEx
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# CcCopyReadEx function


## -description


The <b>CcCopyReadEx</b> routine copies data from a cached file to a user buffer. The I/O byte count for the operation is charged to the issuing thread.


## -syntax


````
BOOLEAN CcCopyReadEx(
  _In_  PFILE_OBJECT     FileObject,
  _In_  PLARGE_INTEGER   FileOffset,
  _In_  ULONG            Length,
  _In_  BOOLEAN          Wait,
  _Out_ PVOID            Buffer,
  _Out_ PIO_STATUS_BLOCK IoStatus,
  _In_  PETHREAD         IoIssuerThread
);
````


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

To cache a file, use <a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>.




## -see-also

<a href="..\ntifs\nf-ntifs-ccsetadditionalcacheattributes.md">CcSetAdditionalCacheAttributes</a>



<a href="..\ntifs\nf-ntifs-ccfastcopyread.md">CcFastCopyRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539191">CcReadAhead</a>



<a href="..\ntifs\nf-ntifs-ccsetreadaheadgranularity.md">CcSetReadAheadGranularity</a>



<a href="..\ntifs\nf-ntifs-ccschedulereadahead.md">CcScheduleReadAhead</a>



<a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcCopyReadEx routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

