---
UID: NF:ntifs.FsRtlIsSystemPagingFile
title: FsRtlIsSystemPagingFile function (ntifs.h)
description: Learn more about the FsRtlIsSystemPagingFile routine.
tech.root: ifsk
ms.date: 07/06/2023
keywords: ["FsRtlIsSystemPagingFile function"]
ms.keywords: FsRtlIsPagingFile, FsRtlIsSystemPagingFile, ifsk.fsrtlissystempagingfile, ntifs/FsRtlIsPagingFile
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlIsSystemPagingFile
 - ntifs/FsRtlIsSystemPagingFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlIsSystemPagingFile
---

# FsRtlIsSystemPagingFile function

## -description

The **FsRtlIsSystemPagingFile** routine determines whether a given file is currently a system paging file.

## -parameters

### -param FileObject [in]

Pointer to a file object for the file.

## -returns

**FsRtlIsSystemPagingFile** returns TRUE if the file represented by **FileObject** is a system paging file, otherwise FALSE.

## -see-also

[**FsRtlIsPagingFile**](nf-ntifs-fsrtlispagingfile.md)

[**FsRtlPostPagingFileStackOverflow**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlpostpagingfilestackoverflow.md)

[**FsRtlSupportsPerStreamContexts**](/previous-versions/ff547285(v=vs.85))
