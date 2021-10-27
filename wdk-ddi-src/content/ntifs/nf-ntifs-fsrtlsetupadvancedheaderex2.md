---
UID: NF:ntifs.FsRtlSetupAdvancedHeaderEx2
tech.root: ifsk
title: FsRtlSetupAdvancedHeaderEx2
ms.date: 09/29/2021
targetos: Windows
description: Learn more about the FsRtlSetupAdvancedHeaderEx2 function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 20H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - FsRtlSetupAdvancedHeaderEx2
f1_keywords:
 - FsRtlSetupAdvancedHeaderEx2
 - ntifs/FsRtlSetupAdvancedHeaderEx2
dev_langs:
 - c++
---

## -description

The **FsRtlSetupAdvancedHeaderEx2** macro is used by file systems to initialize an [**FSRTL_ADVANCED_FCB_HEADER**](ns-ntifs-_fsrtl_advanced_fcb_header.md) structure for use with stream and file contexts.

## -parameters

### -param _advhdr

Pointer to the [**FSRTL_ADVANCED_FCB_HEADER**](ns-ntifs-_fsrtl_advanced_fcb_header.md) structure to be initialized.

### -param _fmutx

Pointer to an initialized fast mutex that will be used to synchronize access to certain [**FSRTL_ADVANCED_FCB_HEADER**](ns-ntifs-_fsrtl_advanced_fcb_header.md) members. The fast mutex must be allocated from nonpaged pool. This parameter is optional and can be **NULL**. Callers should set this parameter to **NULL** if they intend to use an already existing fast mutex object. If **FastMutex** is **NULL**, the caller must explicitly set the **FastMutex** member of the **FSRTL_ADVANCED_FCB_HEADER** structure, contained in the stream context object, to point to the existing fast mutex. (This can be done before or after calling **FsRtlSetupAdvancedHeaderEx2**.)

### -param _fctxptr

A pointer to a pointer field used by the file system runtime library (FSRTL) to track file contexts. This parameter is optional and can be **NULL**. If **FileContextSupportPointer** is not **NULL**, **FileContextSupportPointer** must be a pointer to a PVOID variable inside a per-file structure for the file system that created the structure. To indicate that the file system driver does not support file contexts, callers must set **FileContextSupportPointer** to **NULL**.

### -param _aepushlock

Pointer to an opaque structure used to initialize the **AePushLock** field of the [advanced header](ns-ntifs-_fsrtl_advanced_fcb_header.md). The caller of this function is responsible for first allocating and initializing the memory for this field by calling [**FsRtlAllocateAePushLock**](nf-ntifs-fsrtlallocateaepushlock.md), and subsequently freeing the memory by calling [**FsRtlFreeAePushLock**](nf-ntifs-fsrtlfreeaepushlock.md). See [**FSRTL_ADVANCED_FCB_HEADER**](ns-ntifs-_fsrtl_advanced_fcb_header.md) for more information about auto-expand push locks.

## -remarks

File systems use the **FsRtlSetupAdvancedHeaderEx2** macro to initialize an [**FSRTL_ADVANCED_FCB_HEADER**](ns-ntifs-_fsrtl_advanced_fcb_header.md) structure for use with stream and file contexts.

When the advanced FCB header structure is no longer required, the file system must call [**FsRtlTeardownPerStreamContexts**](nf-ntifs-fsrtlteardownperstreamcontexts.md) to free all associated stream and file context structures.

For more information, see [Tracking Per-Stream Context in a Legacy File System Filter Driver](/windows-hardware/drivers/ifs/tracking-per-stream-context-in-a-legacy-file-system-filter-driver).

## -see-also

[**FSRTL_ADVANCED_FCB_HEADER**](ns-ntifs-_fsrtl_advanced_fcb_header.md)

[**FSRTL_PER_STREAM_CONTEXT**](/previous-versions/ff547357(v=vs.85))

[**FsRtlAllocateAePushLock**](nf-ntifs-fsrtlallocateaepushlock.md)

[**FsRtlFreeAePushLock**](nf-ntifs-fsrtlfreeaepushlock.md)

[**FsRtlInitPerStreamContext**](nf-ntifs-fsrtlinitperstreamcontext.md)

[**FsRtlInsertPerStreamContext**](nf-ntifs-fsrtlinsertperstreamcontext.md)

[**FsRtlLookupPerStreamContext**](nf-ntifs-fsrtllookupperstreamcontext.md)

[**FsRtlRemovePerStreamContext**](nf-ntifs-fsrtlremoveperstreamcontext.md)

[**FsRtlSupportsPerStreamContexts**](/previous-versions/ff547285(v=vs.85))

[**FsRtlTeardownPerStreamContexts**](nf-ntifs-fsrtlteardownperstreamcontexts.md)
