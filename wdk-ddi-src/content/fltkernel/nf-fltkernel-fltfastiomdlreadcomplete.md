---
UID: NF:fltkernel.FltFastIoMdlReadComplete
title: FltFastIoMdlReadComplete function (fltkernel.h)
description: The FltFastIoMdlReadComplete routine completes the read operation that the FltFastIoMdlRead routine initiated.
old-location: ifsk\fltfastiomdlreadcomplete.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltFastIoMdlReadComplete function"]
ms.keywords: FltFastIoMdlReadComplete, FsRtlMdlReadCompleteDev, FsRtlMdlReadCompleteDev routine [Installable File System Drivers], fltkernel/FsRtlMdlReadCompleteDev, ifsk.fltfastiomdlreadcomplete
req.header: fltkernel.h
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
f1_keywords:
 - FltFastIoMdlReadComplete
 - fltkernel/FltFastIoMdlReadComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FltFastIoMdlReadComplete
---

# FltFastIoMdlReadComplete function


## -description

The <b>FltFastIoMdlReadComplete</b> routine completes the read operation that the <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfastiomdlread">FltFastIoMdlRead</a> routine initiated.

## -parameters

### -param InitiatingInstance

Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>.

### -param FileObject [in]


A pointer to the file object.

### -param MdlChain [in]


A pointer to a linked list of memory descriptor lists (MDLs) that the <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfastiomdlread">FltFastIoMdlRead</a> routine allocated.

## -returns

None

## -remarks

The <b>FltFastIoMdlReadComplete</b> routine unlocks the pages in cache memory that the <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfastiomdlread">FltFastIoMdlRead</a> routine allocated.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfastiomdlread">FltFastIoMdlRead</a>

