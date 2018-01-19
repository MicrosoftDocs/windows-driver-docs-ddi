---
UID: NF:ntifs.CcCopyWrite
title: CcCopyWrite function
author: windows-driver-content
description: The CcCopyWrite routine copies data from a user buffer to a cached file.
old-location: ifsk\cccopywrite.htm
old-project: ifsk
ms.assetid: 100fec4a-eebe-4a4d-b322-09afbe68ec5c
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: CcCopyWrite
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available on Microsoft Windows 2000 and later Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CcCopyWrite
req.alt-loc: NtosKrnl.exe
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
req.typenames: TOKEN_TYPE
---

# CcCopyWrite function



## -description
The <b>CcCopyWrite</b> routine copies data from a user buffer to a cached file.



## -syntax

````
BOOLEAN CcCopyWrite(
  _In_ PFILE_OBJECT   FileObject,
  _In_ PLARGE_INTEGER FileOffset,
  _In_ ULONG          Length,
  _In_ BOOLEAN        Wait,
  _In_ PVOID          Buffer
);
````


## -parameters

### -param FileObject [in]

A pointer to a file object for the cached file to which the data is to be written.


### -param FileOffset [in]

A pointer to a variable that specifies the starting byte offset within the cached file.


### -param Length [in]

The length in bytes of the data to be written.


### -param Wait [in]

Set to <b>TRUE</b> if the caller can be put into a wait state until all the data has been copied, <b>FALSE</b> otherwise.


### -param Buffer [in]

A pointer to the buffer from which the data is to be copied.


## -returns
The <b>CcCopyWrite</b> routine returns <b>TRUE</b> if the data was copied successfully, <b>FALSE</b> otherwise.


## -remarks
If <i>Wait</i> is <b>TRUE</b>, <b>CcCopyWrite</b> is guaranteed to complete the copy request and return <b>TRUE</b>. If the required pages of the cached file are already resident in memory, the data will be copied immediately and no blocking will occur. If any needed pages are not resident, the caller will be put in a wait state until all required pages have been made resident and the data can be copied.

If <i>Wait</i> is <b>FALSE</b>, <b>CcCopyWrite</b> will refuse to block, and will return <b>FALSE</b>, if the required pages of the cached file are not already resident in memory or if the FO_WRITE_THROUGH flag is set on the file object.

If any failure occurs, <b>CcCopyWrite</b> raises a status exception for that particular failure. For example, if a pool allocation failure occurs, <b>CcCopyWrite</b> raises a STATUS_INSUFFICIENT_RESOURCES exception; if an I/O error occurs, <b>CcCopyWrite</b> raises the status exception of the I/O error. Therefore, to gain control if a failure occurs, the driver should wrap the call to <b>CcCopyWrite</b> in a <b>try-except</b> or <b>try-finally</b> statement.

To cache a file, use <a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>.


## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcCopyWrite routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

