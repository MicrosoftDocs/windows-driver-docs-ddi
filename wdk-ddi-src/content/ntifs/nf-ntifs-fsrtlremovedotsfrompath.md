---
UID: NF:ntifs.FsRtlRemoveDotsFromPath
title: FsRtlRemoveDotsFromPath function (ntifs.h)
description: The FsRtlRemoveDotsFromPath routine removes unnecessary occurrences of '.' and '..' from the specified path.
old-location: ifsk\fsrtlremovedotsfrompath.htm
tech.root: ifsk
ms.assetid: af6ecdb7-8713-460d-8fd9-ef027ac15b39
ms.date: 04/16/2018
keywords: ["FsRtlRemoveDotsFromPath function"]
ms.keywords: FsRtlRemoveDotsFromPath, FsRtlRemoveDotsFromPath routine [Installable File System Drivers], fsrtlref_93b15313-3292-4122-9852-731b995e9d20.xml, ifsk.fsrtlremovedotsfrompath, ntifs/FsRtlRemoveDotsFromPath
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating system.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlRemoveDotsFromPath
 - ntifs/FsRtlRemoveDotsFromPath
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlRemoveDotsFromPath
---

# FsRtlRemoveDotsFromPath function


## -description

The <b>FsRtlRemoveDotsFromPath</b> routine removes unnecessary occurrences of '.' and '..' from the specified path.

## -parameters

### -param OriginalString 

[in, out]
A pointer to the buffer to be processed.

### -param PathLength 

[in]
The length of buffer (in bytes).

### -param NewLength 

[out]
A pointer to the new length of the buffer, after processing.

## -returns

The<b> FsRtlRemoveDotsFromPath</b> routine returns either STATUS_SUCCESS value for success or STATUS_IO_REPARSE_DATA_INVALID if the operation could not be completed.

## -remarks

This routine would take a path as <i>OriginalString</i> like the following example:


```cpp
\dir1\dir2\..\dir3\.\file.txt
```

The routine would modify <i>OriginalString</i> as follows:


```cpp
\dir1\dir3\file.txt
```

The routine will fail with STATUS_IO_REPARSE_DATA_INVALID if any of the following strings are passed as <i>OriginalString</i>:


```cpp
\..
..
..\anyOtherContent
```


