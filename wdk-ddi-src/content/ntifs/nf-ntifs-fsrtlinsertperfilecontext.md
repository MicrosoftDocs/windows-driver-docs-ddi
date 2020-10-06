---
UID: NF:ntifs.FsRtlInsertPerFileContext
title: FsRtlInsertPerFileContext function (ntifs.h)
description: The FsRtlInsertPerFileContext routine associates a FSRTL_PER_FILE_CONTEXT object with a driver-specified context object for a file.
old-location: ifsk\fsrtlinsertperfilecontext.htm
tech.root: ifsk
ms.assetid: accc3600-9614-48e0-912d-1e8b324e659f
ms.date: 04/16/2018
keywords: ["FsRtlInsertPerFileContext function"]
ms.keywords: FsRtlInsertPerFileContext, FsRtlInsertPerFileContext routine [Installable File System Drivers], fsrtlref_570a2352-733f-4b83-8f63-f4bfed0e2f56.xml, ifsk.fsrtlinsertperfilecontext, ntifs/FsRtlInsertPerFileContext
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating system.
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
req.irql: <=APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlInsertPerFileContext
 - ntifs/FsRtlInsertPerFileContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlInsertPerFileContext
---

# FsRtlInsertPerFileContext function


## -description

The <b>FsRtlInsertPerFileContext</b> routine associates a <a href="/previous-versions/ff547352(v=vs.85)">FSRTL_PER_FILE_CONTEXT</a> object with a driver-specified context object for a file.

## -parameters

### -param PerFileContextPointer 

[in]
A pointer to an opaque pointer used by the file system runtime library (FSRTL) package to track file contexts. To retrieve this pointer from a file object, use the <a href="/previous-versions/ff546051(v=vs.85)">FsRtlGetPerFileContextPointer</a> macro.

### -param Ptr 

[in]
A pointer to the driver-specific context structure.

## -returns

The <b>FsRtlInsertPerFileContext</b> routine returns STATUS_SUCCESS, or an appropriate error code, such as:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The underlying file system does not support filter file contexts. You can use the <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlsupportsperfilecontexts">FsRtlSupportsPerFileContexts</a> macro to check whether a file system supports per file context objects.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The system could not allocate resources (typically memory).

</td>
</tr>
</table>

## -remarks

The FsRtlGetPerFileContextPointer macro returns a <i>FileContextSupportPointer</i> for an open file. 

Parameters

<i>FileObject</i>

<b>FILE_OBJECT</b>

A pointer to a file object.

Return value

<b>PVOID</b>

The FsRtlGetPerFileContextPointer macro returns an opaque pointer used by the file system runtime library (FSRTL) package to track file contexts. The macro returns <b>NULL</b> if the file system does not support the use of per-file context objects with files.

The FsRtlGetPerFileContextPointer macro returns the pointer to be passed to routines such as <b>FsRtlInsertPerFileContext</b>, <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtllookupperfilecontext">FsRtlLookupPerFileContext</a>, and  <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlremoveperfilecontext">FsRtlRemovePerFileContext</a>.

For more information about how to use and create context objects, see <a href="/windows-hardware/drivers/ifs/tracking-per-file-context-in-a-legacy-file-system-filter-driver">Tracking Per-File Context in a Legacy File System Filter Driver</a>.

## -see-also

<a href="/previous-versions/ff547352(v=vs.85)">FSRTL_PER_FILE_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtllookupperfilecontext">FsRtlLookupPerFileContext</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlremoveperfilecontext">FsRtlRemovePerFileContext</a>



<a href="/windows-hardware/drivers/ifs/tracking-per-file-context-in-a-legacy-file-system-filter-driver">Tracking Per-File Context in a Legacy File System Filter Driver</a>