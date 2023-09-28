---
UID: NF:ntifs.FsRtlRemovePerFileContext
title: FsRtlRemovePerFileContext function (ntifs.h)
description: Learn more about the FsRtlRemovePerFileContext function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["FsRtlRemovePerFileContext function"]
ms.keywords: FsRtlRemovePerFileContext, FsRtlRemovePerFileContext routine [Installable File System Drivers], fsrtlref_90f829b2-a8ed-44fd-adb3-61c57f5f9aad.xml, ifsk.fsrtlremoveperfilecontext, ntifs/FsRtlRemovePerFileContext
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows Vista
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
 - FsRtlRemovePerFileContext
 - ntifs/FsRtlRemovePerFileContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlRemovePerFileContext
---

# FsRtlRemovePerFileContext function

## -description

The **FsRtlRemovePerFileContext** routine returns a pointer to a [**FSRTL_PER_FILE_CONTEXT**](/previous-versions/ff547352(v=vs.85)) object that is associated with a file. **FsRtlRemovePerFileContext** removes the **FSRTL_PER_FILE_CONTEXT** object from the list it occupies, along with the associated driver specific context information.

## -parameters

### -param PerFileContextPointer [in]

A pointer to an opaque pointer that is used by the file system runtime library (FSRTL) package to track file contexts. To obtain this pointer from a file object, use the [**FsRtlGetPerFileContextPointer**](/previous-versions/ff546051(v=vs.85)) macro.

### -param OwnerId [in, optional]

A pointer to a filter driver-allocated variable that uniquely identifies the owner of the per-file context structure.  This parameter is optional, but must be non-NULL if **InstanceId** is non-NULL.

### -param InstanceId [in, optional]

A pointer to a filter driver-allocated variable that can be used to distinguish among per-file context structures that are created by the same filter driver.  This parameter is optional.

## -returns

A pointer to the first [**FSRTL_PER_FILE_CONTEXT**](/previous-versions/ff547352(v=vs.85)) that matches the **OwnerId** and **InstanceId**, if specified. If no match is found or if the system does not support per file context information, this routine returns NULL.

## -remarks

**FsRtlRemovePerFileContext** removes only the first matching per-file context structure that it finds. If there are additional matching per-file contexts, the filter driver must call **FsRtlRemovePerFileContext** as many times as required to remove them all.

The file system filter driver must free the memory that is used for this context information after the [**FSRTL_PER_FILE_CONTEXT**](/previous-versions/ff547352(v=vs.85)) has been removed.

Use this routine for your drivers to remove contexts only when the driver must discard per-file context information while the file is still open. Contexts are removed when a file is closed by using [**FsRtlTeardownPerFileContexts**](nf-ntifs-fsrtlteardownperfilecontexts.md).

Don't use this routine inside your **FreeCallback** routine. The file system removes contexts from the list before that routine is called.

Don't use this routine inside your IRP_CLOSE handler. You will not be notified when the stream is torn down.

## -see-also

[**FSRTL_PER_FILE_CONTEXT**](/previous-versions/ff547352(v=vs.85))

[**FsRtlGetPerFileContextPointer**](/previous-versions/ff546051(v=vs.85))

[**FsRtlInsertPerFileContext**](nf-ntifs-fsrtlinsertperfilecontext.md)

[**FsRtlLookupPerFileContext**](nf-ntifs-fsrtllookupperfilecontext.md)

[Tracking Per-File Context in a Legacy File System Filter Driver](/windows-hardware/drivers/ifs/tracking-per-file-context-in-a-legacy-file-system-filter-driver)
