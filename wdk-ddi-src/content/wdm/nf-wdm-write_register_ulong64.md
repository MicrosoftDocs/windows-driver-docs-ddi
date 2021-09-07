---
UID: NF:wdm.WRITE_REGISTER_ULONG64
title: WRITE_REGISTER_ULONG64 function (wdm.h)
description: The WRITE_REGISTER_ULONG64 function (wdm.h) writes a ULONG64 value to the specified register address.
tech.root: kernel
ms.date: 09/07/2021
keywords: ["WRITE_REGISTER_ULONG64 function"]
ms.keywords: WRITE_REGISTER_ULONG64, WRITE_REGISTER_ULONG64 function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available only in 64-bit versions of Windows.
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
req.lib: NtosKrnl.exe
req.dll: NtosKrnl.exe
req.irql: Any level (see Remarks section)
targetos: Windows
req.typenames:
f1_keywords:
 - WRITE_REGISTER_ULONG64
 - wdm/WRITE_REGISTER_ULONG64
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - WRITE_REGISTER_ULONG64
---

# WRITE_REGISTER_ULONG64 function (wdm.h)


## -description

The **WRITE_REGISTER_ULONG64** routine dereferences the supplied pointer, inserts a memory barrier, and writes a ULONG64 value to the specified address.

## -parameters

### -param Register 

[in]
Pointer to the register, which must be a mapped range in memory space.

### -param Value 

[in]
Specifies a ULONG64 value to write to the register.

## -remarks

This routine inserts a memory barrier into your code. This barrier guarantees that every operation that appears in the source code before the call to **WRITE_REGISTER_ULONG** will complete before any operation that appears after the call.

For more info about memory barriers, see [**KeMemoryBarrier**](/windows-hardware/drivers/ddi/wdm/nf-wdm-kememorybarrier).

Callers of the **WRITE_REGISTER_ULONG64** macro can be running at any IRQL, assuming the *Register* register is resident, mapped device memory. 

