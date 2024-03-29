---
UID: NF:ntifs.FsRtlLookupPerStreamContext
title: FsRtlLookupPerStreamContext macro (ntifs.h)
description: The FsRtlLookupPerStreamContext macro retrieves a per-stream context structure for a file stream.
old-location: ifsk\fsrtllookupperstreamcontext.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlLookupPerStreamContext macro"]
ms.keywords: FsRtlLookupPerStreamContext, FsRtlLookupPerStreamContext function [Installable File System Drivers], fsrtlref_8284a485-5669-4a4f-a2cf-d566b82299fb.xml, ifsk.fsrtllookupperstreamcontext, ntifs/FsRtlLookupPerStreamContext
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 2000 SP4 Update Rollup; Windows XP
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlLookupPerStreamContext
 - ntifs/FsRtlLookupPerStreamContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlLookupPerStreamContext
---

# FsRtlLookupPerStreamContext macro


## -description

The <b>FsRtlLookupPerStreamContext</b> macro retrieves a per-stream context structure for a file stream.

## -parameters

### -param _sc

<p>Pointer to the FSRTL_ADVANCED_FCB_HEADER structure for the file stream. To get this pointer from a file object, use the <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlgetperstreamcontextpointer"><b>FsRtlGetPerStreamContextPointer</b></a> macro. </p>

### -param _oid

<p>Pointer to a caller-allocated variable that uniquely identifies the owner of the per-stream context structure. The format of this variable is filter driver − specific. Must be non-<b>NULL</b> if a non-<b>NULL</b> value is supplied for <i>InstanceId</i>. </p>

### -param _iid

<p>Pointer to a filter driver − allocated variable that can be used to distinguish among per-stream context structures created by the same filter driver. The format of this variable is filter driver − specific. </p>
  <p>If <i>OwnerId</i> and <i>InstanceId</i> are both <b>NULL</b>, <b>FsRtlLookupPerStreamContext</b> returns the first per-stream context found. </p>
  <p>If a non-<b>NULL</b> value is supplied for <i>OwnerId</i> and <i>InstanceId</i> is <b>NULL</b>, <b>FsRtlLookupPerStreamContext</b> returns the first per-stream context found whose <b>OwnerId</b> member matches the <i>OwnerId</i> parameter. </p>

## -remarks

A file system filter driver calls <b>FsRtlLookupPerStreamContext</b> to retrieve its per-stream context structure for a file stream. The per-stream context structure contains context information that the filter driver maintains for the file stream. 

<div class="alert"><b>Note</b>  <b>FsRtlLookupPerStreamContext</b>  can only be used on file systems that support per-stream contexts.</div>
<div> </div>
To initialize a per-stream context structure, use the <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlinitperstreamcontext">FsRtlInitPerStreamContext</a> macro. 

To associate an initialized per-stream context structure with a file stream, call <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlinsertperstreamcontext">FsRtlInsertPerStreamContext</a>. 

To remove a per-stream context structure that is associated with a file stream, call <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlremoveperstreamcontext">FsRtlRemovePerStreamContext</a>. 

For more information, see <a href="/windows-hardware/drivers/ifs/tracking-per-stream-context-in-a-legacy-file-system-filter-driver">Tracking Per-Stream Context in a Legacy File System Filter Driver</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a>



<a href="/previous-versions/ff547357(v=vs.85)">FSRTL_PER_STREAM_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlgetperstreamcontextpointer">FsRtlGetPerStreamContextPointer</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlinitperstreamcontext">FsRtlInitPerStreamContext</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlinsertperstreamcontext">FsRtlInsertPerStreamContext</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlremoveperstreamcontext">FsRtlRemovePerStreamContext</a>



<a href="/previous-versions/ff547257(v=vs.85)">FsRtlSetupAdvancedHeader</a>



<a href="/previous-versions/ff547285(v=vs.85)">FsRtlSupportsPerStreamContexts</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlteardownperstreamcontexts">FsRtlTeardownPerStreamContexts</a>
