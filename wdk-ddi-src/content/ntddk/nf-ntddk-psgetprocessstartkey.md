---
UID: NF:ntddk.PsGetProcessStartKey
tech.root: kernel
title: PsGetProcessStartKey
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
 - PsGetProcessStartKey
f1_keywords:
 - PsGetProcessStartKey
 - ntddk/PsGetProcessStartKey
dev_langs:
 - c++
helpviewer_keywords:
 - PsGetProcessStartKey
---

## -description

This routine generates an identifier for a process which is unique across boot sessions.

## -parameters

### -param Process [in]

A pointer to the EPROCESS structure that represents the process. Drivers can use the [**PsGetCurrentProcess**](../wdm/nf-wdm-iogetcurrentprocess.md) and [**ObReferenceObjectByHandle**](../wdm/nf-wdm-obreferenceobjectbyhandle.md) routines to obtain a pointer to the EPROCESS structure for a process.

## -returns

Returns a ULONGLONG specifying a unique identifier for the provided process.

## -remarks

Here is an example of how a driver might call this routine:

```cpp
ULONGLONG ProcessStartKey;
ProcessStartKey = PsGetProcessStartKey(PsGetCurrentProcess());
```

The process start key is typically used to track or identify a process over time.

## -see-also

