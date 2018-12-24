---
UID: NF:ntifs.FsRtlInsertPerFileObjectContext
title: FsRtlInsertPerFileObjectContext function
description: For a &#0034;legacy&#0034; file system filter driver, the FsRtlInsertPerFileObjectContext function associates context information with a file object.
old-location: ifsk\fsrtlinsertperfileobjectcontext.htm
tech.root: ifsk
ms.assetid: 852b8b71-8a8c-4e9e-b27e-78fc2df8d5bd
ms.date: 04/16/2018
ms.keywords: FsRtlInsertPerFileObjectContext, FsRtlInsertPerFileObjectContext function [Installable File System Drivers], fsrtlref_21a21edf-cf20-4c0b-aaef-bc75656238c4.xml, ifsk.fsrtlinsertperfileobjectcontext, ntifs/FsRtlInsertPerFileObjectContext
ms.topic: function
req.header: ntifs.h
req.include-header: Fltkernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlInsertPerFileObjectContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlInsertPerFileObjectContext function


## -description


For a "legacy" file system filter driver, the <b>FsRtlInsertPerFileObjectContext </b>function associates context information with a file object.


## -parameters




### -param FileObject [in]

A pointer to the file object for which to associate context information (given by the <i>Ptr</i> parameter).


### -param Ptr [in]

A pointer to a caller-allocated and initialized FSRTL_PER_FILEOBJECT_CONTEXT structure to be associated with <i>FileObject</i>. The structure can be used as-is or embedded in a driver-defined, per-file-object context information structure. To initialize the structure, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546170">FsRtlInitPerFileObjectContext</a> macro.


## -returns



<b>FsRtlInsertPerFileObjectContext </b>returns an appropriate NTSTATUS value, such as one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The context information structure was successfully associated with the file object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>FileObject</i> parameter is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The system lacks sufficient resources to complete the operation. For example, a file object extension could not be allocated for <i>FileObject</i>.

</td>
</tr>
</table>
 




## -remarks



A file system filter driver calls <b>FsRtlInsertPerFileObjectContext </b>to associate its own per-file-object context structure with a file object. The context structure contains context information that the filter driver maintains for the file object. The <b>FsRtlInsertPerStreamContext</b> function inserts the <i>Ptr</i> context structure into the context list for <i>FileObject</i>.

All per-file-object context information structures must be or contain an initialized FSRTL_PER_FILEOBJECT_CONTEXT structure. Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546170">FsRtlInitPerFileObjectContext</a> macro to initialize a FSRTL_PER_FILEOBJECT_CONTEXT structure.

After a FSRTL_PER_FILEOBJECT_CONTEXT structure or filter-defined per-file-object context structure (containing an initialized FSRTL_PER_FILEOBJECT_CONTEXT structure) has been associated with a file object, it can be retrieved by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff546936">FsRtlLookupPerFileObjectContext</a> or removed by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547232">FsRtlRemovePerFileObjectContext</a>.

<div class="alert"><b>Note</b>    File system minifilter drivers must not use the <b>FsRtl</b><i>Xxx</i><b>PerFileObjectContext</b> functions. Instead, minifilters can use the <b>Flt</b><i>Xxx</i><b>Context</b> functions to associate context information with a file object. For a complete list, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547346">FSRTL_PER_FILEOBJECT_CONTEXT</a> topic.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547346">FSRTL_PER_FILEOBJECT_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546170">FsRtlInitPerFileObjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546936">FsRtlLookupPerFileObjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547232">FsRtlRemovePerFileObjectContext</a>
 

 

