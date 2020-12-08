---
UID: NF:ntifs.FsRtlSetupAdvancedHeaderEx
title: FsRtlSetupAdvancedHeaderEx macro (ntifs.h)
description: The FsRtlSetupAdvancedHeaderEx macro is used by file systems to initialize an FSRTL_ADVANCED_FCB_HEADER structure for use with both stream and file contexts.
old-location: ifsk\fsrtlsetupadvancedheaderex.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlSetupAdvancedHeaderEx macro"]
ms.keywords: FsRtlSetupAdvancedHeaderEx, FsRtlSetupAdvancedHeaderEx function [Installable File System Drivers], fsrtlref_9214990b-2568-43d9-801a-c43514a6448f.xml, ifsk.fsrtlsetupadvancedheaderex, ntifs/FsRtlSetupAdvancedHeaderEx
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Desktop
req.target-min-winverclnt: Available on Update Rollup for Microsoft Windows 2000 Service Pack 4 (SP4) and on Windows XP and later versions of the Windows operating systems.
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlSetupAdvancedHeaderEx
 - ntifs/FsRtlSetupAdvancedHeaderEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - FsRtlSetupAdvancedHeaderEx
---

# FsRtlSetupAdvancedHeaderEx macro


## -description

The <b>FsRtlSetupAdvancedHeaderEx</b> macro is used by file systems to initialize an <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a> structure for use with both stream and file contexts.

## -parameters

### -param _advhdr

<p>Pointer to the <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_fsrtl_advanced_fcb_header"><b>FSRTL_ADVANCED_FCB_HEADER</b></a> structure to be initialized. </p>

### -param _fmutx

<p>Pointer to an initialized fast mutex that will be used to synchronize access to certain FSRTL_ADVANCED_FCB_HEADER members (for more information, see <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_fsrtl_advanced_fcb_header"><b>FSRTL_ADVANCED_FCB_HEADER</b></a>). The fast mutex must be allocated from nonpaged pool. This parameter is optional and can be <b>NULL</b>. Callers should set this parameter to <b>NULL</b> if they intend to use an already existing fast mutex object. If <i>FastMutex</i> is <b>NULL</b>, the caller must explicitly set the <b>FastMutex</b> member of the FSRTL_ADVANCED_FCB_HEADER structure, contained in the stream context object, to point to the existing fast mutex. (This can be done before or after calling <b>FsRtlSetupAdvancedHeaderEx</b>.)</p>

### -param _fctxptr

<p>A pointer to a pointer field used by the file system runtime library (FSRTL) package to track file contexts. </p>
  <p>This parameter is optional and can be <b>NULL</b>.  In particular:</p>
  <ul>
    <li>
      <p> For Microsoft Windows operating systems released prior to Windows Vista: Callers must set this parameter to <b>NULL</b>.</p>
    </li>
    <li>
      <p> For Windows operating systems starting with Windows Vista: If <i>FileContextSupportPointer</i> is not <b>NULL</b>, <i>FileContextSupportPointer</i> must be a pointer to a PVOID variable inside a per-file structure for the file system that created the structure.  To indicate that the file system driver does not support file contexts, callers must set <i>FileContextSupportPointer</i> to <b>NULL</b>.</p>
    </li>
  </ul>

## -remarks

File systems use the <b>FsRtlSetupAdvancedHeaderEx</b> macro to initialize an FSRTL_ADVANCED_FCB_HEADER structure for use with stream and file contexts. 

When the advanced FCB header structure is no longer required, the file system must call <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlteardownperstreamcontexts">FsRtlTeardownPerStreamContexts</a> to free all associated stream and file context structures.

For more information, see <a href="/windows-hardware/drivers/ifs/tracking-per-stream-context-in-a-legacy-file-system-filter-driver">Tracking Per-Stream Context in a Legacy File System Filter Driver</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a>



<a href="/previous-versions/ff547357(v=vs.85)">FSRTL_PER_STREAM_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlgetperstreamcontextpointer">FsRtlGetPerStreamContextPointer</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlinitperstreamcontext">FsRtlInitPerStreamContext</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlinsertperstreamcontext">FsRtlInsertPerStreamContext</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtllookupperstreamcontext">FsRtlLookupPerStreamContext</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlremoveperstreamcontext">FsRtlRemovePerStreamContext</a>



<a href="/previous-versions/ff547285(v=vs.85)">FsRtlSupportsPerStreamContexts</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlteardownperstreamcontexts">FsRtlTeardownPerStreamContexts</a>
