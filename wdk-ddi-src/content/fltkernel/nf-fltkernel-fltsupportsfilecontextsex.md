---
UID: NF:fltkernel.FltSupportsFileContextsEx
title: FltSupportsFileContextsEx function (fltkernel.h)
description: The FltSupportsFileContextsEx routine determines whether the file system or the filter manager support file contexts for a given file.
old-location: ifsk\fltsupportsfilecontextsex.htm
tech.root: ifsk
ms.date: 05/29/2019
keywords: ["FltSupportsFileContextsEx function"]
ms.keywords: FltApiRef_p_to_z_3e8b5485-5c61-4405-9c5d-7d7c966f0478.xml, FltSupportsFileContextsEx, FltSupportsFileContextsEx routine [Installable File System Drivers], fltkernel/FltSupportsFileContextsEx, ifsk.fltsupportsfilecontextsex
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Windows Vista and later.
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltSupportsFileContextsEx
 - fltkernel/FltSupportsFileContextsEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltSupportsFileContextsEx
---

# FltSupportsFileContextsEx function


## -description

The **FltSupportsFileContextsEx** routine determines whether the file system or the filter manager support file contexts for a given file.

## -parameters

### -param FileObject 

[in]
Pointer to the file object that represents the file whose file context support is being queried. This parameter is required and cannot be **NULL**.

### -param Instance 

[in, optional]
Opaque instance pointer for the caller. This parameter is optional and can be **NULL**. For more information about this parameter, see the Remarks section of this page.

## -returns

**FltSupportsFileContextsEx** returns **TRUE** if the file system or filter manager supports file contexts for the file; **FALSE** otherwise.

## -remarks

Minifilter drivers can call the **FltSupportsFileContextsEx** routine to determine whether the underlying file system or the filter manager supports file contexts for the file represented by *FileObject* without having to allocate a context and attempt to set it. If a context type isn't supported on a file, then the minifilter cannot attach a context to that file.

For file systems (such as FAT) that support only a single data stream per file, file contexts are equivalent to stream contexts. Such file systems usually support stream contexts but do not support file contexts. Instead, the filter manager provides file context support, using the file system's existing support for stream contexts. For minifilter instances attached to these file systems, [FltSupportsFileContexts](nf-fltkernel-fltsupportsfilecontexts.md) returns **FALSE**, while **FltSupportsFileContextsEx** returns **TRUE** (when a valid non-**NULL** value is passed for the *Instance* parameter).

If a non-**NULL** value is supplied for the *Instance* parameter, **FltSupportsFileContextsEx** returns **TRUE** if the file system or the filter manager supports file contexts for the file; **FALSE** otherwise.

If the *Instance* parameter is **NULL**, **FltSupportsFileContextsEx** returns **TRUE** only if the file system supports file contexts for the file. Otherwise, it returns **FALSE**, even if the filter manager supports file contexts for the file.

Note that a file system might support file contexts for some types of files but not for others. For example, NTFS and FAT do not support file contexts for paging files.

For more information about contexts, see [Managing Contexts in a Minifilter Driver](/windows-hardware/drivers/ifs/managing-contexts-in-a-minifilter-driver).

## -see-also

[FltAllocateContext](nf-fltkernel-fltallocatecontext.md)

[FltDeleteContext](nf-fltkernel-fltdeletecontext.md)

[FltDeleteFileContext](nf-fltkernel-fltdeletefilecontext.md)

[FltGetFileContext](nf-fltkernel-fltgetfilecontext.md)

[FltReleaseContext](nf-fltkernel-fltreleasecontext.md)

[FltSetFileContext](nf-fltkernel-fltsetfilecontext.md)

[FltSupportsFileContexts](nf-fltkernel-fltsupportsfilecontexts.md)
