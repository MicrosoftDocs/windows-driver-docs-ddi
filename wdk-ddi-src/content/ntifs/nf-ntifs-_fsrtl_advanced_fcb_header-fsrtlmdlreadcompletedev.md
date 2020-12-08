---
UID: NF:ntifs.FsRtlMdlReadCompleteDev
title: FsRtlMdlReadCompleteDev function (ntifs.h)
description: The FsRtlMdlReadCompleteDev routine completes the read operation that the FsRtlMdlReadDev routine initiated.
old-location: ifsk\fsrtlmdlreadcompletedev.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlMdlReadCompleteDev function"]
ms.keywords: FsRtlMdlReadCompleteDev, FsRtlMdlReadCompleteDev routine [Installable File System Drivers], ntifs/FsRtlMdlReadCompleteDev, ifsk.fsrtlmdlreadcompletedev
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
ms.custom: RS5
f1_keywords:
 - FsRtlMdlReadCompleteDev
 - ntifs/FsRtlMdlReadCompleteDev
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlMdlReadCompleteDev
dev_langs:
 - c++
---

# FsRtlMdlReadCompleteDev function


## -description

The <b>FsRtlMdlReadCompleteDev</b> routine completes the read operation that the <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlmdlreaddev">FsRtlMdlReadDev</a> routine initiated.

## -parameters

### -param FileObject 

[in]
A pointer to the file object.

### -param MdlChain 

[in]
On return, a pointer to a linked list of one or more MDLs that point to the cached file data.

### -param DeviceObject 

[ in, optional ]
A pointer to a device object on which the file is opened.

## -returns

None

## -remarks

The <b>FsRtlMdlReadCompleteDev</b> routine unlocks the pages in cache memory that the <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlmdlreaddev">FsRtlMdlReadDev</a> routine allocated.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlmdlreaddev">FsRtlMdlReadDev</a>
