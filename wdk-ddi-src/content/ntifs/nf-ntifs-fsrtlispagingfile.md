---
UID: NF:ntifs.FsRtlIsPagingFile
title: FsRtlIsPagingFile function
author: windows-driver-content
description: The FsRtlIsPagingFile routine determines whether a given file is a paging file.
old-location: ifsk\fsrtlispagingfile.htm
old-project: ifsk
ms.assetid: 85363a0b-0e62-499e-bcdb-4b86c4a0c3a0
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlIsPagingFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Update Rollup for Windows 2000 Service Pack 4 (SP4) and on Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlIsPagingFile
req.alt-loc: NtosKrnl.exe
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
req.typenames: TOKEN_TYPE
---

# FsRtlIsPagingFile function



## -description
The <b>FsRtlIsPagingFile</b> routine determines whether a given file is a paging file. 



## -syntax

````
LOGICAL FsRtlIsPagingFile(
  _In_ PFILE_OBJECT FileObject
);
````


## -parameters

### -param FileObject [in]

Pointer to a file object for the file. 


## -returns
<b>FsRtlIsPagingFile</b> returns <b>TRUE</b> if the file represented by <i>FileObject</i> is a paging file, otherwise <b>FALSE</b>.


## -remarks
File system filter drivers call <b>FsRtlIsPagingFile</b> to determine whether a given file object represents a paging file. 


## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlpostpagingfilestackoverflow~r2.md">FsRtlPostPagingFileStackOverflow</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547285">FsRtlSupportsPerStreamContexts</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlIsPagingFile routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

