---
UID: NF:ntddk.IoSetFileObjectIgnoreSharing
title: IoSetFileObjectIgnoreSharing function (ntddk.h)
description: The IoSetFileObjectIgnoreSharing routine sets a file object to ignore file sharing access checks.
tech.root: ifsk
ms.date: 04/20/2023
keywords: ["IoSetFileObjectIgnoreSharing function"]
ms.keywords: IoSetFileObjectIgnoreSharing, IoSetFileObjectIgnoreSharing routine [Installable File System Drivers], ifsk.iosetfileobjectignoresharing, ntddk/IoSetFileObjectIgnoreSharing
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows 7.
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
 - IoSetFileObjectIgnoreSharing
 - ntddk/IoSetFileObjectIgnoreSharing
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoSetFileObjectIgnoreSharing
---

## -description

The **IoSetFileObjectIgnoreSharing** routine sets a file object to ignore file  sharing access checks.

## -parameters

### -param FileObject

Pointer to a file object for the file.

## -returns

**IoSetFileObjectIgnoreSharing** returns STATUS_SUCCESS or an appropriate NTSTATUS code such as one of the following:

| Return code | Description |
|--|--|
| **STATUS_NOT_FOUND** | The option information for *FileObject* was not found. The status of sharing access checking cannot be set. |
| **STATUS_INSUFFICIENT_RESOURCES** | The option information was not created for *FileObject*. The status of sharing access checking cannot be set. |

## -see-also

[IoIsFileObjectIgnoringSharing](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioisfileobjectignoringsharing)
