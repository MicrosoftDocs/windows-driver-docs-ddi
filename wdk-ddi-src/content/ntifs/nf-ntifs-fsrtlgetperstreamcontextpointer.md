---
UID: NF:ntifs.FsRtlGetPerStreamContextPointer
title: FsRtlGetPerStreamContextPointer macro (ntifs.h)
description: The FsRtlGetPerStreamContextPointer macro returns the file system's stream context for a file stream.
old-location: ifsk\fsrtlgetperstreamcontextpointer.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlGetPerStreamContextPointer macro"]
ms.keywords: FsRtlGetPerStreamContextPointer, FsRtlGetPerStreamContextPointer function [Installable File System Drivers], fsrtlref_c7e152d7-1815-435e-852a-975962e355a6.xml, ifsk.fsrtlgetperstreamcontextpointer, ntifs/FsRtlGetPerStreamContextPointer
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: The FsRtlGetPerStreamContextPointer macro is available on Microsoft Windows XP and later, and on the Update Rollup for Windows 2000 Service Pack 4 (SP4).
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlGetPerStreamContextPointer
 - ntifs/FsRtlGetPerStreamContextPointer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - FsRtlGetPerStreamContextPointer
---

# FsRtlGetPerStreamContextPointer macro


## -description

The <b>FsRtlGetPerStreamContextPointer</b> macro returns the file system's stream context for a file stream.

## -parameters

### -param _fo

<p>Pointer to a file object for the file stream. </p>

## -remarks

File system filter drivers can use the <b>FsRtlGetPerStreamContextPointer</b> macro to obtain a stream context pointer for the file stream that is represented by a given file object. A stream context pointer is a pointer to the file system's stream context for the file stream. This pointer can be passed as a parameter to <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlinsertperstreamcontext">FsRtlInsertPerStreamContext</a>, <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtllookupperstreamcontext">FsRtlLookupPerStreamContext</a>, and <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlremoveperstreamcontext">FsRtlRemovePerStreamContext</a>. 

The stream context pointer points to a <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a> structure that uniquely identifies the file stream to the file system. This structure is usually embedded in a stream context object, such as a file control block (FCB) or stream control block (SCB). When the file stream is opened, the file system stores a pointer to the FCB or SCB in the file object's <b>FsContext</b> member. 

<div class="alert"><b>Note</b>    The <b>FsRtlGetPerStreamContextPointer</b> macro can only be used on file systems that support advanced FCB headers.</div>
<div> </div>
For more information, see <a href="/windows-hardware/drivers/ifs/tracking-per-stream-context-in-a-legacy-file-system-filter-driver">Tracking Per-Stream Context in a Legacy File System Filter Driver</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlinitperstreamcontext">FsRtlInitPerStreamContext</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlinsertperstreamcontext">FsRtlInsertPerStreamContext</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtllookupperstreamcontext">FsRtlLookupPerStreamContext</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlremoveperstreamcontext">FsRtlRemovePerStreamContext</a>



<a href="/previous-versions/ff547257(v=vs.85)">FsRtlSetupAdvancedHeader</a>



<a href="/previous-versions/ff547285(v=vs.85)">FsRtlSupportsPerStreamContexts</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlteardownperstreamcontexts">FsRtlTeardownPerStreamContexts</a>
