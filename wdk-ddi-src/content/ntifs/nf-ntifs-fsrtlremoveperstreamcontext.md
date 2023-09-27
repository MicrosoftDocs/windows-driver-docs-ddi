---
UID: NF:ntifs.FsRtlRemovePerStreamContext
title: FsRtlRemovePerStreamContext function (ntifs.h)
description: Learn more about the FsRtlRemovePerStreamContext function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["FsRtlRemovePerStreamContext function"]
ms.keywords: FsRtlRemovePerStreamContext, FsRtlRemovePerStreamContext function [Installable File System Drivers], fsrtlref_904bd4dd-c254-4762-8af6-dcc49aaa5c92.xml, ifsk.fsrtlremoveperstreamcontext, ntifs/FsRtlRemovePerStreamContext
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
 - FsRtlRemovePerStreamContext
 - ntifs/FsRtlRemovePerStreamContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlRemovePerStreamContext
---

# FsRtlRemovePerStreamContext function

## -description

**FsRtlRemovePerStreamContext** removes a per-stream context structure from the list of per-stream contexts associated with a file stream.

## -parameters

### -param StreamContext [in]

Pointer to the FSRTL_ADVANCED_FCB_HEADER structure for the file stream. To get this pointer from a file object, use the [**FsRtlGetPerStreamContextPointer**](nf-ntifs-fsrtlgetperstreamcontextpointer.md) macro.

### -param OwnerId [in, optional]

Used to identify context information as belonging to a particular filter driver.

### -param InstanceId [in, optional]

Used to search for a particular instance of a per-stream context. If not provided, any of the contexts owned by the filter driver is removed and returned.

If neither the **OwnerId** nor the **InstanceId** is provided, any associated per-stream context will be removed and returned.

## -returns

**FsRtlRemovePerStreamContext** returns a pointer to the per-stream context that is removed. If no match is found, or if the file system does not support filter contexts, **FsRtlRemovePerStreamContext** returns NULL.

## -remarks

A file system filter driver calls **FsRtlRemovePerStreamContext** to remove its own per-stream context structure from the list of per-stream contexts associated with a file stream.

**FsRtlRemovePerStreamContext** removes only the first matching per-stream context structure that is found. If there are additional matching per-stream contexts, the filter driver must call **FsRtlRemovePerStreamContext** as many times as required to remove them all.

This routine should only be used when a filter driver needs to discard the context information it has associated with a file stream while the stream is still open. For example, a filter driver might call **FsRtlRemovePerStreamContext** in the following cases:

* When it receives a request from a user-mode application to stop logging I/O requests on a particular volume.

* When it detects that a file or directory has been renamed.

When a file stream is closed, the file system is responsible for ensuring that all per-stream contexts associated with that stream are removed and freed. To do this, the file system must call [**FsRtlTeardownPerStreamContexts**](nf-ntifs-fsrtlteardownperstreamcontexts.md) on the file control block (FCB) or other stream context object for the file stream. **FsRtlTeardownPerStreamContexts** walks the FilterContexts list, removing each entry and calling its **FreeCallback** routine.

Thus, a file system filter driver should not call **FsRtlRemovePerStreamContext** from within an IRP_MJ_CLOSE or IRP_MJ_PNP dispatch routine. Not only would such a call be unnecessary, but it might also interfere with the file system's call to [**FsRtlTeardownPerStreamContexts**](nf-ntifs-fsrtlteardownperstreamcontexts.md).

A file system filter driver should not call **FsRtlRemovePerStreamContext** from within a per-stream context structure's **FreeCallback** routine. This is because the underlying file system calls the **FreeCallback** routine after it has already removed the context structure from the FilterContexts list.

To initialize a per-stream context structure, use the [**FsRtlInitPerStreamContext**](nf-ntifs-fsrtlinitperstreamcontext.md) macro.

To associate an initialized per-stream context structure with a file stream, call [**FsRtlInsertPerStreamContext**](nf-ntifs-fsrtlinsertperstreamcontext.md).

To retrieve a per-stream context structure that is associated with a file stream, call [**FsRtlLookupPerStreamContext**](nf-ntifs-fsrtllookupperstreamcontext.md).

**FsRtlRemovePerStreamContext** can only be used on file systems that support filter contexts.

For more information, see [Tracking Per-Stream Context in a Legacy File System Filter Driver](/windows-hardware/drivers/ifs/tracking-per-stream-context-in-a-legacy-file-system-filter-driver).

## -see-also

[**FSRTL_ADVANCED_FCB_HEADER**](ns-ntifs-_fsrtl_advanced_fcb_header.md)

[**FSRTL_PER_STREAM_CONTEXT**](/previous-versions/ff547357(v=vs.85))

[**FsRtlGetPerStreamContextPointer**](nf-ntifs-fsrtlgetperstreamcontextpointer.md)

[**FsRtlInitPerStreamContext**](nf-ntifs-fsrtlinitperstreamcontext.md)

[**FsRtlInsertPerStreamContext**](nf-ntifs-fsrtlinsertperstreamcontext.md)

[**FsRtlLookupPerStreamContext**](nf-ntifs-fsrtllookupperstreamcontext.md)

[**FsRtlSetupAdvancedHeader**](/previous-versions/ff547257(v=vs.85))

[**FsRtlSupportsPerStreamContexts**](/previous-versions/ff547285(v=vs.85))

[**FsRtlTeardownPerStreamContexts**](nf-ntifs-fsrtlteardownperstreamcontexts.md)

[**IRP_MJ_CLOSE**](/windows-hardware/drivers/kernel/irp-mj-close)

[**IRP_MJ_PNP**](/windows-hardware/drivers/ifs/irp-mj-pnp)
