---
UID: NF:ntifs.FsRtlSetKernelEaFile
title: FsRtlSetKernelEaFile function
author: windows-driver-content
description: The routine FsRtlQueryKernelEaFile is used to set, modify and/or delete extended attribute (EA) values for a file and synchronously wait for it to complete, returning a result.
old-location: ifsk\fsrtlsetkerneleafile.htm
old-project: ifsk
ms.assetid: E5EA2E40-2CC3-4C7B-8BCC-4793F76ECBAD
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FsRtlSetKernelEaFile, FsRtlSetKernelEaFile routine [Installable File System Drivers], ifsk.fsrtlsetkerneleafile, ntifs/FsRtlSetKernelEaFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	FsRtlSetKernelEaFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlSetKernelEaFile function


## -description


The routine <b>FsRtlQueryKernelEaFile</b> is used to set, modify and/or delete extended attribute (EA) values for a file and synchronously wait
    for it to complete, returning a result.  It sets the <b>IRP_MN_KERNEL</b> minor
    code which allows this API to set SecureEAs.  This allows the caller to do
    this by FileObject instead of a handle.


## -parameters




### -param FileObject [in]

A pointer to a <b>FileObject</b> to send the QueryEA request to.


### -param EaBuffer [in]

A pointer to a caller-supplied, <a href="https://msdn.microsoft.com/library/windows/hardware/ff545793">FILE_FULL_EA_INFORMATION</a>-structured input buffer that contains the extended attribute values to be set


### -param Length [in]

Specifies the length of the EA buffer.


## -returns



The routine <b>FsRtlSetKernelEaFile</b> receives the status of the operation and returns one of the status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_EA_LIST_INCONSISTENT </b></dt>
</dl>
</td>
<td width="60%">
The <b>EaList</b> parameter is not formatted correctly.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_EAS_NOT_SUPPORTED  </b></dt>
</dl>
</td>
<td width="60%">
The file system does not support extended attributes.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The  I/O request packet (IRP) could not be allocated for this request.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INTERMIXED_KERNEL_EA_OPERATION</b></dt>
</dl>
</td>
<td width="60%">
The request cannot intermix normal and kernel EA’s in the same call.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The request failed as it was a direct device open.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The request was successful. 

</td>
</tr>
</table>
 




## -remarks



 This routine assumes all passed in buffers are from kernel mode.

One or more Kernel EA’s may be set, modified and/or deleted in a single call to <b>FsRtlSetKernelEaFile</b>. Normal EA’s may also be set using the <b>FsRtlSetKernelEaFile</b> function.
You delete EA’s by specifying an <b>EAName</b> with an <b>EaValueLength</b> of zero.  You can intermix inserting new, modifying existing, or removing EA’s in a single call.




## -see-also




<a href="https://msdn.microsoft.com/B57BC3A4-6116-48EA-905A-CFA7AC0A5E8F">FsRtlQueryKernelEaFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff961907">ZwQueryEaFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff961908">ZwSetEaFile</a>
 

 

