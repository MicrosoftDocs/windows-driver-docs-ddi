---
UID: NF:fltkernel.FltSupportsFileContexts
title: FltSupportsFileContexts function (fltkernel.h)
description: The FltSupportsFileContexts routine determines whether the file system supports file contexts for a given file.
old-location: ifsk\fltsupportsfilecontexts.htm
tech.root: ifsk
ms.date: 01/22/2021
keywords: ["FltSupportsFileContexts function"]
ms.keywords: FltApiRef_p_to_z_cad3f45c-7ae0-44dc-840d-a8ec3da65ea6.xml, FltSupportsFileContexts, FltSupportsFileContexts routine [Installable File System Drivers], fltkernel/FltSupportsFileContexts, ifsk.fltsupportsfilecontexts
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
 - FltSupportsFileContexts
 - fltkernel/FltSupportsFileContexts
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltSupportsFileContexts
---

# FltSupportsFileContexts function

## -description

The **FltSupportsFileContexts** routine determines whether the file system supports file contexts for a given file. (See also [FltSupportsFileContextsEx](nf-fltkernel-fltsupportsfilecontextsex.md).)

## -parameters

### -param FileObject [in]

Pointer to the file object that represents the file whose file context support is being queried. This parameter is required and cannot be **NULL**.

## -returns

**FltSupportsFileContexts** returns **TRUE** if the file system supports file contexts for the file object; **FALSE** otherwise.

## -remarks

Minifilter drivers call **FltSupportsFileContexts** to determine whether the underlying file system inherently supports file contexts for the file that is represented by the specified *FileObject* without having to allocate a context and attempt to set it. If a context type isn't supported on a file, then the minifilter cannot attach a context to that file.

Note that a file system might support file contexts for some types of files but not for others. For example, NTFS and FAT do not support file contexts for paging files.

For more information about contexts, see [About minifilter contexts](/windows-hardware/drivers/ifs/managing-contexts-in-a-minifilter-driver).

## -see-also

[FltAllocateContext](nf-fltkernel-fltallocatecontext.md)

[FltDeleteContext](nf-fltkernel-fltdeletecontext.md)

[FltDeleteFileContext](nf-fltkernel-fltdeletefilecontext.md)

[FltGetFileContext](nf-fltkernel-fltgetfilecontext.md)

[FltReleaseContext](nf-fltkernel-fltreleasecontext.md)

[FltSetFileContext](nf-fltkernel-fltsetfilecontext.md)

[FltSupportsFileContextsEx](nf-fltkernel-fltsupportsfilecontextsex.md)
