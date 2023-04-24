---
UID: NF:ntddk.PsAllocSiloContextSlot
title: PsAllocSiloContextSlot function (ntddk.h)
description: This routine allocates a slot that can be used to insert, retrieve, and delete an object in all silos.
tech.root: kernel
ms.date: 04/20/2023
keywords: ["PsAllocSiloContextSlot function"]
ms.keywords: PsAllocSiloContextSlot, PsAllocSiloContextSlot routine [Kernel-Mode Driver Architecture], kernel.psallocsilocontextslot, ntddk/PsAllocSiloContextSlot
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PsAllocSiloContextSlot
 - ntddk/PsAllocSiloContextSlot
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - PsAllocSiloContextSlot
---

## -description

This routine allocates a slot that can be used to insert, retrieve, and delete an object in all silos.

## -parameters

### -param Reserved [in]

This parameter is reserved for future use and **must be set to zero**.

### -param ReturnedContextSlot [out]

A pointer to a caller-allocated variable that receives the newly allocated slot index. This parameter is required and it cannot be **NULL**.

## -returns

The following NT status codes are returned.

| Return code | Description |
|--|--|
| **STATUS_INSUFFICIENT_RESOURCES** | There are no more slots available in the system. This is an error code. |
| **STATUS_SUCCESS** | The operation completed successfully. |

## -remarks

Use of this API is uncommon because all silo monitors are assigned a storage slot when calling the [PsRegisterSiloMonitor](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psregistersilomonitor) routine.  That slot can be retrieved with the [PsGetSiloMonitorContextSlot](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetsilomonitorcontextslot) routine and used by a driver for its context operations.

## -see-also

[PsFreeSiloContextSlot](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psfreesilocontextslot)
