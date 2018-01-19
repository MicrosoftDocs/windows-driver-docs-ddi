---
UID: NF:ntifs.CcSetFileSizes
title: CcSetFileSizes function
author: windows-driver-content
description: The CcSetFileSizes routine updates the cache maps and section object for a cached file whose size has changed.
old-location: ifsk\ccsetfilesizes.htm
old-project: ifsk
ms.assetid: 1fc92167-ceab-4f8e-bd80-a8f1821846ed
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: CcSetFileSizes
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
req.alt-api: CcSetFileSizes
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
req.irql: 
req.typenames: TOKEN_TYPE
---

# CcSetFileSizes function



## -description
The <b>CcSetFileSizes</b> routine updates the cache maps and section object for a cached file whose size has changed.



## -syntax

````
VOID CcSetFileSizes(
  _In_ PFILE_OBJECT   FileObject,
  _In_ PCC_FILE_SIZES FileSizes
);
````


## -parameters

### -param FileObject [in]

Pointer to a file object for the cached file.


### -param FileSizes [in]

Pointer to a CC_FILE_SIZES structure containing <b>AllocationSize</b>, <b>FileSize</b> and <b>ValidDataLength</b> for the file. This structure is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _CC_FILE_SIZES {
    LARGE_INTEGER AllocationSize;
    LARGE_INTEGER FileSize;
    LARGE_INTEGER ValidDataLength;
} CC_FILE_SIZES, *PCC_FILE_SIZES;</pre>
</td>
</tr>
</table></span></div>
<table>
<tr>
<th>Member</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>AllocationSize</b>

</td>
<td>
New section object size for the file. 

</td>
</tr>
<tr>
<td>
<b>FileSize</b>

</td>
<td>
New file size for the file.

</td>
</tr>
<tr>
<td>
<b>ValidDataLength</b>

</td>
<td>
New valid data length for the file.

</td>
</tr>
</table>
 


## -returns
None


## -remarks
File systems must call <b>CcSetFileSizes</b> to update the cache manager data structures whenever one of the following changes is made to a cached file:

Its allocation size is increased.

Its valid data length is decreased.

Its valid data length is increased by a non-cached I/O operation.

Its file size is increased or decreased.

If any failure occurs, <b>CcSetFileSizes</b> raises a status exception for that particular failure. For example, if a pool allocation failure occurs, <b>CcSetFileSizes</b> raises a STATUS_INSUFFICIENT_RESOURCES exception. Therefore, to gain control if a failure occurs, the driver should wrap the call to <b>CcSetFileSizes</b> in a <b>try-except</b> or <b>try-finally</b> statement.

To cache a file, use <a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>.

The <b>CcGetFileSizePointer</b> macro returns the size of a file, given a pointer to a file object for the file.

Parameters


## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcSetFileSizes routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

