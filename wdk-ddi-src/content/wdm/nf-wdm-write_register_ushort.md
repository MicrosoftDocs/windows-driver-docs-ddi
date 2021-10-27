---
UID: NF:wdm.WRITE_REGISTER_USHORT
title: WRITE_REGISTER_USHORT function (wdm.h)
description: The WRITE_REGISTER_USHORT function (wdm.h) writes a USHORT value to the specified register address in resident, mapped device memory.
old-location: kernel\write_register_ushort.htm
tech.root: kernel
ms.date: 09/07/2021
keywords: ["WRITE_REGISTER_USHORT function"]
ms.keywords: WRITE_REGISTER_USHORT, WRITE_REGISTER_USHORT routine [Kernel-Mode Driver Architecture], k103_bc20d667-b3c7-4e46-a21d-06123e73d348.xml, kernel.write_register_ushort, wdm/WRITE_REGISTER_USHORT
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
 - WRITE_REGISTER_USHORT
 - wdm/WRITE_REGISTER_USHORT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - WRITE_REGISTER_USHORT
---

# WRITE_REGISTER_USHORT function (wdm.h)


## -description

The **WRITE_REGISTER_USHORT** routine dereferences the supplied pointer, inserts a memory barrier, and writes a USHORT value to the specified address.

## -parameters

#### - Register [in]

Pointer to the register, which must be a mapped range in memory space.


#### - Value [in]

Specifies a USHORT value to be written to the register.

## -remarks

This routine inserts a memory barrier into your code. This barrier guarantees that every operation that appears in the source code before the call to this routine will complete before any operation that appears after the call.

For more info about memory barriers, see [**KeMemoryBarrier**](./nf-wdm-kememorybarrier.md).

Callers of <b>WRITE_REGISTER_USHORT</b> can be running at any IRQL, assuming the <i>Register</i> is resident, mapped device memory.