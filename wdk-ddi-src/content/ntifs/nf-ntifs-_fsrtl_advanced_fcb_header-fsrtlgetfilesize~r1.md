---
UID: NF:ntifs.FsRtlGetFileSize~r1
title: FsRtlGetFileSize function (ntifs.h)
description: The FsRtlGetFileSize routine is used to get the size of a file.
old-location: ifsk\fsrtlgetfilesize.htm
tech.root: ifsk
ms.assetid: 82fcf0da-e945-4cb4-90fc-bb095119ef20
ms.date: 03/29/2018
ms.keywords: FsRtlGetFileSize, FsRtlGetFileSize routine [Installable File System Drivers], fsrtlref_d1056cd3-20f5-436c-9bac-0f1c217bb569.xml, ifsk.fsrtlgetfilesize, ntifs/FsRtlGetFileSize
ms.topic: function
f1_keywords:
 - "ntifs/FsRtlGetFileSize"
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlGetFileSize
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlGetFileSize function


## -description


The <b>FsRtlGetFileSize</b> routine is used to get the size of a file.


## -parameters




### -param FileObject [in]

A pointer to the file object to query.


### -param FileSize [out]

A pointer to a large integer that receives the file size on output.


## -returns



<b>FsRtlGetFileSize</b> returns STATUS_SUCCESS or an appropriate error status representing the final completion status of the operation. Possible error status codes include the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The memory required for use by this function could not be allocated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FILE_IS_A_DIRECTORY</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>FileObject </i>refers to a directory.

</td>
</tr>
</table>
 




## -remarks



The <b>FsRtlGetFileSize</b> routine is used to retrieve the file size for a file. Unlike <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a>, <b>FsRtlGetFileSize</b> does not acquire the file object lock on synchronous file objects. If you already own file system resources, you should call <b>FsRtlGetFileSize</b> instead of <b>ZwQueryInformationFile</b>, because attempting to acquire the file object lock would violate locking order and lead to deadlocks. The <b>ZwQueryInformationFile</b> function should be only if you do not already own file system resources.

<b>FsRtlGetFileSize</b> will use fast I/O if it is supported or regular IRP-based query to extract the file size.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryinformationfile">FltQueryInformationFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a>
 

 

