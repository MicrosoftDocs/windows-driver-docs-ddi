---
UID: NF:wdm.WRITE_REGISTER_UCHAR
title: WRITE_REGISTER_UCHAR function (wdm.h)
description: The WRITE_REGISTER_UCHAR function (wdm.h) writes a byte to the specified register address in resident, mapped device memory.
old-location: kernel\write_register_uchar.htm
tech.root: kernel
ms.date: 09/07/2021
keywords: ["WRITE_REGISTER_UCHAR function"]
ms.keywords: WRITE_REGISTER_UCHAR, WRITE_REGISTER_UCHAR routine [Kernel-Mode Driver Architecture], k103_052039f1-0f3c-4b4b-9061-ea92046f7167.xml, kernel.write_register_uchar, wdm/WRITE_REGISTER_UCHAR
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
 - WRITE_REGISTER_UCHAR
 - wdm/WRITE_REGISTER_UCHAR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - WRITE_REGISTER_UCHAR
---

# WRITE_REGISTER_UCHAR function (wdm.h)


## -description

The **WRITE_REGISTER_UCHAR** routine dereferences the supplied pointer, inserts a memory barrier, and writes a UCHAR value to the specified address.

### -parameters

### -param Register [in]

Pointer to the register, which must be a mapped range in memory space.


### -param Value [in]

Specifies a byte to be written to the register.

## -remarks

This routine inserts a memory barrier into your code. This barrier guarantees that every operation that appears in the source code before the call to this routine will complete before any operation that appears after the call.

For more info about memory barriers, see [**KeMemoryBarrier**](./nf-wdm-kememorybarrier.md).

Callers of <b>WRITE_REGISTER_UCHAR</b> can be running at any IRQL, assuming the <i>Register</i> is resident, mapped device memory.