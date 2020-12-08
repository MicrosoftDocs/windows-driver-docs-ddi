---
UID: NF:ntifs.FsRtlMdlReadCompleteDev(PFILE_OBJECT,PMDL,PDEVICE_OBJECT)
title: FsRtlMdlReadCompleteDev function (ntifs.h)
description: The FltFastIoMdlReadComplete routine completes the read operation that the FltFastIoMdlRead routine initiated.
old-location: ifsk\fltfastiomdlreadcomplete.htm
tech.root: ifsk
ms.date: 03/29/2018
keywords: ["FsRtlMdlReadCompleteDev function"]
ms.keywords: FsRtlMdlReadCompleteDev, FsRtlMdlReadCompleteDev routine [Installable File System Drivers], fltkernel/FsRtlMdlReadCompleteDev, ifsk.fltfastiomdlreadcomplete
f1_keywords:
 - "ntifs/FsRtlMdlReadCompleteDev"
 - "FsRtlMdlReadCompleteDev"
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
req.typenames: VOLUME_READ_PLEX_INPUT, *PVOLUME_READ_PLEX_INPUT
dev_langs:
 - c++
ms.custom: RS5
---

# FsRtlMdlReadCompleteDev function


## -description


The <b>FltFastIoMdlReadComplete</b> routine completes the read operation that the <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlmdlreaddev">FltFastIoMdlRead</a> routine initiated.


## -parameters




### -param FileObject 
[in]
A pointer to the file object.


### -param MdlChain 
[in]
On return, a pointer to a linked list of one or more MDLs that point to the cached file data.


### -param DeviceObject

<p>On return, a pointer to a linked list of one or more MDLs that point to the cached file data.</p>




## -returns



None




## -remarks



The <b>FltFastIoMdlReadComplete</b> routine unlocks the pages in cache memory that the <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlmdlreaddev">FltFastIoMdlRead</a> routine allocated.




## -see-also




<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlmdlreaddev">FltFastIoMdlRead</a>
 

 
