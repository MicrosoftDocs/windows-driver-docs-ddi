---
UID: NF:ntifs.FsRtlTeardownPerStreamContexts
title: FsRtlTeardownPerStreamContexts function (ntifs.h)
description: The FsRtlTeardownPerStreamContexts routine frees all per-stream context structures associated with a given FSRTL_ADVANCED_FCB_HEADER structure.
old-location: ifsk\fsrtlteardownperstreamcontexts.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlTeardownPerStreamContexts function"]
ms.keywords: FsRtlTeardownPerStreamContexts, FsRtlTeardownPerStreamContexts routine [Installable File System Drivers], fsrtlref_15f597e3-b397-497b-9839-a61b6cf27745.xml, ifsk.fsrtlteardownperstreamcontexts, ntifs/FsRtlTeardownPerStreamContexts
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Update Rollup for Windows 2000 Service Pack 4 (SP4) and on Microsoft Windows XP and later.
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
 - FsRtlTeardownPerStreamContexts
 - ntifs/FsRtlTeardownPerStreamContexts
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlTeardownPerStreamContexts
---

# FsRtlTeardownPerStreamContexts function


## -description

The <b>FsRtlTeardownPerStreamContexts</b> routine frees all per-stream context structures associated with a given FSRTL_ADVANCED_FCB_HEADER structure.

## -parameters

### -param AdvancedHeader 

[in]
Pointer to the FSRTL_ADVANCED_FCB_HEADER structure.

## -remarks

File systems call <b>FsRtlTeardownPerStreamContexts</b> to free all per-stream context structures associated with a given FSRTL_ADVANCED_FCB_HEADER structure. When a file system tears down the stream context object for a file stream, it must call <b>FsRtlTeardownPerStreamContexts</b>, which in turn calls the <i>FreeCallback</i> routines of all per-stream context structures associated with the file stream. 

To avoid conflicts in synchronization, the <b>FsRtlTeardownPerStreamContexts</b> routine releases the lock for the per file context objects before calling <i>FreeCallback</i>. This avoids blocking access to the to the per file context objects by the filter for own list operations, such as removal with <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlremoveperstreamcontext">FsRtlRemovePerStreamContext</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a>



<a href="/previous-versions/ff547357(v=vs.85)">FSRTL_PER_STREAM_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlgetperstreamcontextpointer">FsRtlGetPerStreamContextPointer</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlinitperstreamcontext">FsRtlInitPerStreamContext</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlinsertperstreamcontext">FsRtlInsertPerStreamContext</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtllookupperstreamcontext">FsRtlLookupPerStreamContext</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlremoveperstreamcontext">FsRtlRemovePerStreamContext</a>



<a href="/previous-versions/ff547257(v=vs.85)">FsRtlSetupAdvancedHeader</a>



<a href="/previous-versions/ff547285(v=vs.85)">FsRtlSupportsPerStreamContexts</a>



<a href="/windows-hardware/drivers/ifs/tracking-per-stream-context-in-a-legacy-file-system-filter-driver">Tracking Per-Stream Context in a Legacy File System Filter Driver</a>
