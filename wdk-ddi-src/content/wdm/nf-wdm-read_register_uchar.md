---
UID: NF:wdm.READ_REGISTER_UCHAR
title: READ_REGISTER_UCHAR function (wdm.h)
description: The READ_REGISTER_UCHAR function (wdm.h) returns a byte read from the specified register address in resident, mapped device memory.
old-location: kernel\read_register_uchar.htm
tech.root: kernel
ms.date: 09/07/2021
keywords: ["READ_REGISTER_UCHAR function"]
ms.keywords: READ_REGISTER_UCHAR, READ_REGISTER_UCHAR routine [Kernel-Mode Driver Architecture], k103_b7970afc-0b18-49c4-b873-a9fd689c0c97.xml, kernel.read_register_uchar, wdm/READ_REGISTER_UCHAR
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Ioaccess.h, Miniport.h, Wudfwdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: Any level (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - READ_REGISTER_UCHAR
 - wdm/READ_REGISTER_UCHAR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - READ_REGISTER_UCHAR
---

# READ_REGISTER_UCHAR function (wdm.h)


## -description

The **READ_REGISTER_UCHAR** routine dereferences the supplied pointer, inserts a memory barrier, and reads a byte from the specified register address.

### -parameters

### -param Register [in]

Pointer to the register address, which must be a mapped range in memory space.

## -returns

<b>READ_REGISTER_UCHAR</b> returns the byte read from the specified register address.

## -remarks

This routine inserts a memory barrier into your code. This barrier guarantees that every operation that appears in the source code before the call to this routine will complete before any operation that appears after the call.

For more info about memory barriers, see [**KeMemoryBarrier**](./nf-wdm-kememorybarrier.md).

Callers of <b>READ_REGISTER_UCHAR</b> can be running at any IRQL, assuming the <i>Register</i> is resident, mapped device memory.