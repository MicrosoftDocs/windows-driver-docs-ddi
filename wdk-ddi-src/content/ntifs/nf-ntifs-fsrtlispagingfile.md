---
UID: NF:ntifs.FsRtlIsPagingFile
title: FsRtlIsPagingFile function (ntifs.h)
description: The FsRtlIsPagingFile routine determines whether a given file is a paging file.
old-location: ifsk\fsrtlispagingfile.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlIsPagingFile function"]
ms.keywords: FsRtlIsPagingFile, FsRtlIsPagingFile routine [Installable File System Drivers], fsrtlref_80254cb1-bb65-4b1b-8fe4-c975b0f00c63.xml, ifsk.fsrtlispagingfile, ntifs/FsRtlIsPagingFile
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Update Rollup for Windows 2000 Service Pack 4 (SP4) and on Windows XP and later.
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
 - FsRtlIsPagingFile
 - ntifs/FsRtlIsPagingFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlIsPagingFile
---

# FsRtlIsPagingFile function


## -description

The <b>FsRtlIsPagingFile</b> routine determines whether a given file is a paging file.

## -parameters

### -param FileObject 

[in]
Pointer to a file object for the file.

## -returns

<b>FsRtlIsPagingFile</b> returns <b>TRUE</b> if the file represented by <i>FileObject</i> is a paging file, otherwise <b>FALSE</b>.

## -remarks

File system filter drivers call <b>FsRtlIsPagingFile</b> to determine whether a given file object represents a paging file. 

<div class="alert"><b>Note</b>    If <b>FsRtlIsPagingFile</b> is called in the create completion ("post-create") path, it returns <b>FALSE</b>, even if the file is a paging file. However, it works properly on Windows Vista and later. </div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlpostpagingfilestackoverflow">FsRtlPostPagingFileStackOverflow</a>



<a href="/previous-versions/ff547285(v=vs.85)">FsRtlSupportsPerStreamContexts</a>
