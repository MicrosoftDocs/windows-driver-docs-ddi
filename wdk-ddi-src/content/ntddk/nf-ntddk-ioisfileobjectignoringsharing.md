---
UID: NF:ntddk.IoIsFileObjectIgnoringSharing
title: IoIsFileObjectIgnoringSharing function (ntddk.h)
description: The IoIsFileObjectIgnoringSharing routine determines if a file object is set with the option to ignore file sharing access checks.
old-location: ifsk\ioisfileobjectignoringsharing.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["IoIsFileObjectIgnoringSharing function"]
ms.keywords: IoIsFileObjectIgnoringSharing, IoIsFileObjectIgnoringSharing routine [Installable File System Drivers], ifsk.ioisfileobjectignoringsharing, ntddk/IoIsFileObjectIgnoringSharing
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows Vista.
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
req.irql: Any
targetos: Windows
req.typenames: 
f1_keywords:
 - IoIsFileObjectIgnoringSharing
 - ntddk/IoIsFileObjectIgnoringSharing
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoIsFileObjectIgnoringSharing
---

# IoIsFileObjectIgnoringSharing function


## -description

The <b>IoIsFileObjectIgnoringSharing</b> routine determines if a file object is set with the option to ignore file  sharing access checks.

## -parameters

### -param FileObject

Pointer to a file object for the file.

## -returns

<b>TRUE</b> if file sharing access checks are ignored. Otherwise, <b>FALSE</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iosetfileobjectignoresharing">IoSetFileObjectIgnoreSharing</a>
