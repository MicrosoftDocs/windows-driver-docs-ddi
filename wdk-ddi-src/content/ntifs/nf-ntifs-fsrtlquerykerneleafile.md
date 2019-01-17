---
UID: NF:ntifs.FsRtlQueryKernelEaFile
title: FsRtlQueryKernelEaFile function
description: The routine FsRtlQueryKernelEaFile is used to build an explicit QueryEA request and synchronously wait for it to complete, returning the result. This allows the caller to do this by FileObject instead of a handle.
old-location: ifsk\fsrtlquerykerneleafile.htm
tech.root: ifsk
ms.assetid: B57BC3A4-6116-48EA-905A-CFA7AC0A5E8F
ms.date: 04/16/2018
ms.keywords: FsRtlQueryKernelEaFile, FsRtlQueryKernelEaFile routine [Installable File System Drivers], ifsk.fsrtlquerykerneleafile, ntifs/FsRtlQueryKernelEaFile
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
-	FsRtlQueryKernelEaFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlQueryKernelEaFile function


## -description


The routine <b>FsRtlQueryKernelEaFile</b> is used to build an explicit QueryEA request and synchronously wait
    for it to complete, returning the result. This allows the caller to do
    this by FileObject instead of a handle.


## -parameters




### -param FileObject [in]

A pointer to a <b>FileObject</b> to send the QueryEA request to.


### -param ReturnedEaData [out]

A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff545793">FILE_FULL_EA_INFORMATION</a>-structured output buffer, where the extended attribute values are to be returned.


### -param Length [in]

Specifies the length, in bytes, of <b>ReturnedEaData</b>


### -param ReturnSingleEntry [in]

Specifies whether only a single entry should be returned
        rather than filling the buffer with as many EAs as possible.


### -param EaList [in]

A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff540295">FILE_GET_EA_INFORMATION</a>-structured input buffer, which specifies the extended attributes to be queried. This parameter is optional and can be<b> NULL</b>.


### -param EaListLength [in]

Specifies the length of <b>EaList</b>, if an EA list was
        supplied.


### -param EaIndex [in, optional]

Supplies the optional index of an EA whose value is to be
        returned.  If specified, then only that EA is returned.


### -param RestartScan [in]

Specifies whether the scan of the EAs should be restarted
        from the beginning.


### -param LengthReturned [out, optional]

Specifies the amount of valid data that is returned in the
        <b>ReturnedEaData</b> buffer.


## -returns



The routine <b>FsRtlQueryKernelEaFile</b> returns one of the status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_EAS_NOT_SUPPORTED </b></dt>
</dl>
</td>
<td width="60%">
The file system does not support extended attributes.

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
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The request was successful.

</td>
</tr>
</table>
 




## -remarks



This routine <b>FsRtlQueryKernelEaFile </b>assumes all passed in buffers are from kernel mode as it  requires that the given Input and Output buffers if specified, be kernel mode addresses.  The operation will fail if a user mode address is specified. 




## -see-also




<a href="https://msdn.microsoft.com/E5EA2E40-2CC3-4C7B-8BCC-4793F76ECBAD">FsRtlSetKernelEaFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff961907">ZwQueryEaFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff961908">ZwSetEaFile</a>
 

 

