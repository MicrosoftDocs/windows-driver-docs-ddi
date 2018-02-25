---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlGetFileSize~r1
title: FsRtlGetFileSize function
author: windows-driver-content
description: The FsRtlGetFileSize routine is used to get the size of a file.
old-location: ifsk\fsrtlgetfilesize.htm
old-project: ifsk
ms.assetid: 82fcf0da-e945-4cb4-90fc-bb095119ef20
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , F, FsRtlGetFileSize, FsRtlGetFileSize routine [Installable File System Drivers], G, R, S, e, fsrtlref_d1056cd3-20f5-436c-9bac-0f1c217bb569.xml, i, ifsk.fsrtlgetfilesize, l, ntifs/FsRtlGetFileSize, s, t, z"
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlGetFileSize
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlGetFileSize function


## -description


The <b>FsRtlGetFileSize</b> routine is used to get the size of a file. 


## -syntax


````
NTSTATUS FsRtlGetFileSize(
  _In_  PFILE_OBJECT   FileObject,
  _Out_ PLARGE_INTEGER FileSize
);
````


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



The <b>FsRtlGetFileSize</b> routine is used to retrieve the file size for a file. Unlike <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>, <b>FsRtlGetFileSize</b> does not acquire the file object lock on synchronous file objects. If you already own file system resources, you should call <b>FsRtlGetFileSize</b> instead of <b>ZwQueryInformationFile</b>, because attempting to acquire the file object lock would violate locking order and lead to deadlocks. The <b>ZwQueryInformationFile</b> function should be only if you do not already own file system resources. 

<b>FsRtlGetFileSize</b> will use fast I/O if it is supported or regular IRP-based query to extract the file size. 




## -see-also

<a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>



<a href="..\fltkernel\nf-fltkernel-fltqueryinformationfile.md">FltQueryInformationFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlGetFileSize routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

