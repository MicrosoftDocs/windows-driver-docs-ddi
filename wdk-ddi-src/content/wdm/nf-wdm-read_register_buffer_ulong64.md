---
UID: NF:wdm.READ_REGISTER_BUFFER_ULONG64
title: READ_REGISTER_BUFFER_ULONG64 function (wdm.h)
description: The READ_REGISTER_BUFFER_ULONG64 function (wdm.h)reads a number of ULONG64 values from the specified register address into a buffer.
old-location: wdf\read_register_buffer_ulong64.htm
tech.root: kernel
ms.date: 09/07/2021
keywords: ["READ_REGISTER_BUFFER_ULONG64 function"]
ms.keywords: READ_REGISTER_BUFFER_ULONG64, READ_REGISTER_BUFFER_ULONG64 function
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
 - READ_REGISTER_BUFFER_ULONG64
 - wdm/READ_REGISTER_BUFFER_ULONG64
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - READ_REGISTER_BUFFER_ULONG64
---

# READ_REGISTER_BUFFER_ULONG64 function (wdm.h)

## -description

The **READ_REGISTER_BUFFER_ULONG64** routine dereferences the supplied pointer, inserts a memory barrier, and reads a set of ULONG64 values from the specified register address into a buffer

### -parameters

### -paramparam Register [in]


Pointer to the register address, which must be a mapped range in memory space.

### -paramparam Buffer [out]


Pointer to a buffer that an array of ULONG64 values is read into. 

### -paramparam Count [in]


Specifies the number of ULONG64 values to be read into the buffer.

## -remarks

This routine inserts a memory barrier into your code. This barrier guarantees that every operation that appears in the source code before the call to this routine will complete before any operation that appears after the call.

For more info about memory barriers, see [**KeMemoryBarrier**](./nf-wdm-kememorybarrier.md).

The size of the *Buffer* buffer must be large enough to contain at least the specified number of ULONG64 values.

Callers of the **READ_REGISTER_BUFFER_ULONG64** macro can be running at any IRQL, assuming that the *Buffer* buffer is resident and the *Register* register is resident, mapped device memory.