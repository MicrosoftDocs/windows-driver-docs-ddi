---
UID: NF:ntifs.FsRtlQueryCachedVdl
title: FsRtlQueryCachedVdl function (ntifs.h)
description: The current valid data length (VDL) for a cached file is retrieved with the FsRtlQueryCachedVdl routine.
old-location: ifsk\fsrtlquerycachedvdl.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlQueryCachedVdl function"]
ms.keywords: FsRtlQueryCachedVdl, FsRtlQueryCachedVdl routine [Installable File System Drivers], ifsk.fsrtlquerycachedvdl, ntifs/FsRtlQueryCachedVdl
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in starting with Windows 8.
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
 - FsRtlQueryCachedVdl
 - ntifs/FsRtlQueryCachedVdl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlQueryCachedVdl
---

# FsRtlQueryCachedVdl function


## -description

The current valid data length (VDL) for a cached file is retrieved with the <b>FsRtlQueryCachedVdl</b> routine.

## -parameters

### -param FileObject 

[in]
The file object to retrieve the cached VDL for.

### -param Vdl 

[out]
 A pointer to a caller supplied value which receives the VDL.

## -returns

<b>FsRtlQueryCachedVdl</b> returns <b>STATUS_SUCCESS</b> if the cached VDL is obtained successfully for the <i>FileObject</i> specified. Otherwise, another appropriate <b>NTSTATUS</b> value is returned.

## -remarks

The <b>FsRtlQueryCachedVdl</b> routine will return the VDL for a full span file region. This is a region beginning at an offset of 0 and having a length of <b>MAXLONGLONG</b>.

