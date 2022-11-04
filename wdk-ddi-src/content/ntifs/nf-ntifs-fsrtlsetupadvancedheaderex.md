---
UID: NF:ntifs.FsRtlSetupAdvancedHeaderEx
title: FsRtlSetupAdvancedHeaderEx macro (ntifs.h)
description: The FsRtlSetupAdvancedHeaderEx macro is used by file systems to initialize an FSRTL_ADVANCED_FCB_HEADER structure for use with both stream and file contexts.
old-location: ifsk\fsrtlsetupadvancedheaderex.htm
tech.root: ifsk
ms.date: 09/29/2021
keywords: ["FsRtlSetupAdvancedHeaderEx macro"]
ms.keywords: FsRtlSetupAdvancedHeaderEx, FsRtlSetupAdvancedHeaderEx function [Installable File System Drivers], fsrtlref_9214990b-2568-43d9-801a-c43514a6448f.xml, ifsk.fsrtlsetupadvancedheaderex, ntifs/FsRtlSetupAdvancedHeaderEx
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Desktop
req.target-min-winverclnt: Update Rollup for Microsoft Windows 2000 Service Pack 4 (SP4); Windows XP
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

The **FsRtlSetupAdvancedHeaderEx** macro is used by file systems to initialize an [**FSRTL_ADVANCED_FCB_HEADER**](ns-ntifs-_fsrtl_advanced_fcb_header.md) structure for use with both stream and file contexts.

## -parameters

### -param _advhdr

Pointer to the [**FSRTL_ADVANCED_FCB_HEADER**](ns-ntifs-_fsrtl_advanced_fcb_header.md) structure to be initialized.

### -param _fmutx

Pointer to an initialized fast mutex that will be used to synchronize access to certain [**FSRTL_ADVANCED_FCB_HEADER**](ns-ntifs-_fsrtl_advanced_fcb_header.md) members. The fast mutex must be allocated from nonpaged pool. This parameter is optional and can be **NULL**. Callers should set this parameter to **NULL** if they intend to use an already existing fast mutex object. If **FastMutex** is **NULL**, the caller must explicitly set the **FastMutex** member of the **FSRTL_ADVANCED_FCB_HEADER** structure, contained in the stream context object, to point to the existing fast mutex. (This can be done before or after calling **FsRtlSetupAdvancedHeaderEx**.)

### -param _fctxptr

A pointer to a pointer field used by the file system runtime library (FSRTL) to track file contexts. This parameter is optional and can be **NULL**. In particular:

* For Microsoft Windows operating systems released prior to Windows Vista, callers must set this parameter to **NULL**.

* For Windows operating systems starting with Windows Vista: If **FileContextSupportPointer** is not **NULL**, **FileContextSupportPointer** must be a pointer to a PVOID variable inside a per-file structure for the file system that created the structure. To indicate that the file system driver does not support file contexts, callers must set **FileContextSupportPointer** to **NULL**.

## -remarks

File systems use the **FsRtlSetupAdvancedHeaderEx** macro to initialize an FSRTL_ADVANCED_FCB_HEADER structure for use with stream and file contexts.

When the advanced FCB header structure is no longer required, the file system must call [**FsRtlTeardownPerStreamContexts**](nf-ntifs-fsrtlteardownperstreamcontexts.md) to free all associated stream and file context structures.

For more information, see [Tracking Per-Stream Context in a Legacy File System Filter Driver](/windows-hardware/drivers/ifs/tracking-per-stream-context-in-a-legacy-file-system-filter-driver).

## -see-also

[**FSRTL_ADVANCED_FCB_HEADER**](ns-ntifs-_fsrtl_advanced_fcb_header.md)

[**FSRTL_PER_STREAM_CONTEXT**](/previous-versions/ff547357(v=vs.85))

[**FsRtlGetPerStreamContextPointer**](nf-ntifs-fsrtlgetperstreamcontextpointer.md)

[**FsRtlInitPerStreamContext**](nf-ntifs-fsrtlinitperstreamcontext.md)

[**FsRtlInsertPerStreamContext**](nf-ntifs-fsrtlinsertperstreamcontext.md)

[**FsRtlLookupPerStreamContext**](nf-ntifs-fsrtllookupperstreamcontext.md)

[**FsRtlRemovePerStreamContext**](nf-ntifs-fsrtlremoveperstreamcontext.md)

[**FsRtlSupportsPerStreamContexts**](/previous-versions/ff547285(v=vs.85))

[**FsRtlTeardownPerStreamContexts**](nf-ntifs-fsrtlteardownperstreamcontexts.md)
