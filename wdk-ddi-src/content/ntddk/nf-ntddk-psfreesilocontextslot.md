---
UID: NF:ntddk.PsFreeSiloContextSlot
title: PsFreeSiloContextSlot function (ntddk.h)
description: This routine frees the specified slot and makes it available in the system. It undoes the effects of the PsAllocSiloContextSlot routine.
tech.root: kernel
ms.date: 12/07/2022
keywords: ["PsFreeSiloContextSlot function"]
ms.keywords: PsFreeSiloContextSlot, PsFreeSiloContextSlot routine [Kernel-Mode Driver Architecture], kernel.psfreesilocontextslot, ntddk/PsFreeSiloContextSlot
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
 - PsFreeSiloContextSlot
 - ntddk/PsFreeSiloContextSlot
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - PsFreeSiloContextSlot
---

## -description

This routine  frees the specified slot and makes it available in the system. It undoes the effects of the  [PsAllocSiloContextSlot](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psallocsilocontextslot) routine.

## -parameters

### -param ContextSlot [in]

A slot allocated by the [PsAllocSiloContextSlot](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psallocsilocontextslot) routine.

> [!WARNING]
> Setting this parameter to a slot that is still in use causes the system to execute bug check.

## -returns

The following NT status codes are returned:

| Return code | Description |
|---|---|
| **STATUS_INVALID_PARAMETER** | The slot is not allocated in the system. This is an error code. |
| **STATUS_SUCCESS** | The operation completed successfully. |

## -see-also

[PsAllocSiloContextSlot](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psallocsilocontextslot)
