---
UID: NF:ntifs.FsRtlIsSystemPagingFile
title: FsRtlIsSystemPagingFile function
author: windows-driver-content
description: The FsRtlIsSystemPagingFile routine determines whether a given file is currently a system paging file.
old-location: ifsk\fsrtlissystempagingfile.htm
tech.root: ifsk
ms.assetid: BF92ADEA-4A9F-41E0-BE52-0794D1D827A1
ms.date: 4/16/2018
ms.keywords: FsRtlIsPagingFile, FsRtlIsPagingFile routine [Installable File System Drivers], FsRtlIsSystemPagingFile, ifsk.fsrtlissystempagingfile, ntifs/FsRtlIsPagingFile
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlIsPagingFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlIsSystemPagingFile function


## -description


The <b>FsRtlIsSystemPagingFile</b> routine determines whether a given file is currently a system paging file. 


## -parameters




### -param FileObject [in]

Pointer to a file object for the file. 


## -returns



<b>FsRtlIsSystemPagingFile</b> returns <b>TRUE</b> if the file represented by <i>FileObject</i> is a system paging file, otherwise <b>FALSE</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546873">FsRtlIsPagingFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547152">FsRtlPostPagingFileStackOverflow</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547285">FsRtlSupportsPerStreamContexts</a>
 

 

