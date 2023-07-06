---
UID: NF:ntifs.IoReplaceFileObjectName
title: IoReplaceFileObjectName function (ntifs.h)
description: Learn more about the IoReplaceFileObjectName routine.
tech.root: ifsk
ms.date: 07/06/2023
keywords: ["IoReplaceFileObjectName function"]
ms.keywords: IoReplaceFileObjectName, ntifs/IoReplaceFileObjectName
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 7
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
 - IoReplaceFileObjectName
 - ntifs/IoReplaceFileObjectName
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoReplaceFileObjectName
---

# IoReplaceFileObjectName function

## -description

The **IoReplaceFileObjectName** routine replaces the name of a file object.

## -parameters

### -param FileObject [in]

Pointer to the file object whose file name is being replaced.

### -param NewFileName [in]

Pointer to the string buffer for the new name for the file object.

### -param FileNameLength [in]

Length, in bytes, of the new name for the file object.

## -returns

Returns STATUS_SUCCESS or one of the following NTSTATUS values otherwise:

| Return code | Description |
| ----------- | ----------- |
| STATUS_INVALID_PARAMETER      | The provided file object doesn't have a name to replace. |
| STATUS_INSUFFICIENT_RESOURCES | Inadequate memory is available to allocate a buffer to complete this operation. |

## -remarks

Drivers should use **IoReplaceFileObjectName** to safely replace the name in a file object. This allows the I/O manager to control the lifetime of the buffer associated with the file object. Replacing a file object name directly without using **IoReplaceFileObjectName** may conflict with other uses of the name and should be avoided when possible.

This routine should be used to replace the file object name instead of doing so manually to allow the kernel to manage the lifetime of the name correctly.
