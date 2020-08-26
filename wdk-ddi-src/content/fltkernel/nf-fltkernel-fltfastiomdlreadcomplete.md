---
UID: NF:fltkernel.FltFastIoMdlReadComplete
title: FltFastIoMdlReadComplete function (fltkernel.h)
description: The FltFastIoMdlReadComplete routine completes the read operation that the FltFastIoMdlRead routine initiated.
old-location: ifsk\fltfastiomdlreadcomplete.htm
tech.root: ifsk
ms.assetid: 6F5E808C-9E35-4BE8-AE67-FDD354D6FD0E
ms.date: 04/16/2018
keywords: ["FltFastIoMdlReadComplete function"]
ms.keywords: FltFastIoMdlReadComplete, FsRtlMdlReadCompleteDev, FsRtlMdlReadCompleteDev routine [Installable File System Drivers], fltkernel/FsRtlMdlReadCompleteDev, ifsk.fltfastiomdlreadcomplete
f1_keywords:
 - "fltkernel/FsRtlMdlReadCompleteDev"
 - "FsRtlMdlReadCompleteDev"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlMdlReadCompleteDev
targetos: Windows
req.typenames: 
---

# FltFastIoMdlReadComplete function


## -description


The <b>FltFastIoMdlReadComplete</b> routine completes the read operation that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfastiomdlread">FltFastIoMdlRead</a> routine initiated.


## -parameters




### -param InitiatingInstance

Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param FileObject 
[in]
A pointer to the file object.


### -param MdlChain 
[in]
A pointer to a linked list of memory descriptor lists (MDLs) that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfastiomdlread">FltFastIoMdlRead</a> routine allocated.


## -returns



None




## -remarks



The <b>FltFastIoMdlReadComplete</b> routine unlocks the pages in cache memory that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfastiomdlread">FltFastIoMdlRead</a> routine allocated.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfastiomdlread">FltFastIoMdlRead</a>
 

 

