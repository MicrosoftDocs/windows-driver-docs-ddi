---
UID: NF:ntddk.PsGetThreadCreateTime
tech.root: kernel
title: PsGetThreadCreateTime
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
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 1507
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
 - PsGetThreadCreateTime
f1_keywords:
 - PsGetThreadCreateTime
 - ntddk/PsGetThreadCreateTime
dev_langs:
 - c++
helpviewer_keywords:
 - PsGetThreadCreateTime
---

## -description

This routine retrieves the creation time of a given thread.

## -parameters

### -param Thread [in]

A pointer to an executive thread object structure (ETHREAD) for which to get the creation time.

## -returns

Returns a long long integer that represents the thread's creation time in 100-nanosecond intervals since January 1, 1601. This is a standard timestamp format used in Windows known as FILETIME.

## -remarks

A driver might call PsGetThreadCreateTime for several reasons:

* Debugging and Logging: The creation time of a thread can be useful information when debugging or logging system behavior.

* Performance Monitoring: The creation time can be used in performance monitoring to identify long-lived threads that might be a performance concern.

## -see-also

