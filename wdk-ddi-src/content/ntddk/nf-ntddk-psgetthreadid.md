---
UID: NF:ntddk.PsGetThreadId
tech.root: kernel
title: PsGetThreadId
ms.date: 02/12/2024
targetos: Windows
description: 
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntddk.h
req.idl: 
req.include-header: 
req.irql: DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - PsGetThreadId
f1_keywords:
 - PsGetThreadId
 - ntddk/PsGetThreadId
dev_langs:
 - c++
helpviewer_keywords:
 - PsGetThreadId
---

## -description

This routine returns the unique identifier (ID) of a given thread.

## -parameters

### -param Thread [in]

A pointer to an executive thread object structure (ETHREAD).

## -returns

Returns a HANDLE that is the unique ID of the caller-supplied thread.

## -remarks

A driver might call PsGetThreadId for several reasons:

* Thread Identification: The thread ID returned by PsGetThreadId is unique system-wide, not just within a single process.

* Debugging and Logging: Thread IDs are often used in debugging and logging to trace the execution of the program.

Thread ID is not unique for a boot session. After a thread has terminated its ID may be reused.

## -see-also

