---
UID: NF:ntifs.ZwQueryEaFile
title: ZwQueryEaFile function (ntifs.h)
description: The ZwQueryEaFile routine returns information about extended-attribute (EA) values for a file.
old-location: kernel\zwqueryeafile.htm
tech.root: kernel
ms.assetid: c4261a83-3c91-4bc1-93bf-d2d04c324e94
ms.date: 04/30/2018
ms.keywords: ZwQueryEaFile, ZwQueryEaFile routine [Kernel-Mode Driver Architecture], kernel.zwqueryeafile, ntifs/ZwQueryEaFile
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 2000 and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ZwQueryEaFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwQueryEaFile function


## -description


The <b>ZwQueryEaFile</b> routine returns 
    information about extended-attribute (EA) values for a file.


## -parameters




### -param FileHandle [in]

The handle for the file on which the operation is to be performed.


### -param IoStatusBlock [out]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a> structure that 
      receives the final completion status and other information about the requested operation.


### -param Buffer [out]

A pointer to a caller-supplied 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff545793">FILE_FULL_EA_INFORMATION</a>-structured output 
      buffer, where the extended attribute values are to be returned.


### -param Length [in]

The length, in bytes, of the buffer that the <i>Buffer</i> parameter points to.


### -param ReturnSingleEntry [in]

Set to <b>TRUE</b> if 
      <b>ZwQueryEaFile</b> should return only the first entry that 
      is found.


### -param EaList [in, optional]

A pointer to a caller-supplied 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff540295">FILE_GET_EA_INFORMATION</a>-structured input 
      buffer, which specifies the extended attributes to be queried. This parameter is optional and can be 
      <b>NULL</b>.


### -param EaListLength [in]

The length, in bytes, of the buffer that the <i>EaList</i> parameter points to.


### -param EaIndex [in, optional]

The index of the entry at which scanning the file's extended-attribute list should begin. This parameter is 
      ignored if the <i>EaList</i> parameter points to a nonempty list. This parameter is optional 
      and can be <b>NULL</b>.


### -param RestartScan [in]

Set to <b>TRUE</b> if 
      <b>ZwQueryEaFile</b> should begin the scan at the first 
      entry in the file's extended-attribute list. If this parameter is set to <b>FALSE</b>, the 
      routine resumes the scan from a previous call to 
      <b>ZwQueryEaFile</b>.


## -returns



<b>ZwQueryEaFile</b> returns 
      <b>STATUS_SUCCESS</b> or an appropriate <b>NTSTATUS</b> value such as 
      the following:

<table>
<tr>
<th>Return value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_EAS_NOT_SUPPORTED</dt>
</dl>
</td>
<td width="60%">
The file system does not support extended attributes. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_INSUFFICIENT_RESOURCES</dt>
</dl>
</td>
<td width="60%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff961907">ZwQueryEaFile</a> routine encountered a pool 
        allocation failure. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_EA_LIST_INCONSISTENT</dt>
</dl>
</td>
<td width="60%">
The <i>EaList</i> parameter is not formatted correctly. This is an error code.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545793">FILE_FULL_EA_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540295">FILE_GET_EA_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff961908">ZwSetEaFile</a>
 

 

