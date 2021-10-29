---
UID: NF:wdm.READ_REGISTER_BUFFER_UCHAR
title: READ_REGISTER_BUFFER_UCHAR function (wdm.h)
description: The READ_REGISTER_BUFFER_UCHAR function (wdm.h) reads a number of bytes from the specified register address into a buffer.
old-location: kernel\read_register_buffer_uchar.htm
tech.root: kernel
ms.date: 09/07/2021
keywords: ["READ_REGISTER_BUFFER_UCHAR function"]
ms.keywords: READ_REGISTER_BUFFER_UCHAR, READ_REGISTER_BUFFER_UCHAR routine [Kernel-Mode Driver Architecture], k103_053aab44-4a1f-4eb3-a052-ee00f16a349d.xml, kernel.read_register_buffer_uchar, wdm/READ_REGISTER_BUFFER_UCHAR
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h, Wudfwdm.h
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
 - READ_REGISTER_BUFFER_UCHAR
 - wdm/READ_REGISTER_BUFFER_UCHAR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - READ_REGISTER_BUFFER_UCHAR
---

# READ_REGISTER_BUFFER_UCHAR function (wdm.h)


## -description

The **READ_REGISTER_BUFFER_UCHAR** routine dereferences the supplied pointer, inserts a memory barrier, and reads a set of bytes from the specified register address into a buffer.

### -parameters

#### -param Register [in]


Pointer to the register, which must be a mapped range in memory space.

#### -param Buffer [out]


Pointer to a buffer into which an array of UCHAR values is read.

#### -param Count [in]


Specifies the number of bytes to be read into the buffer.

## -remarks

This routine inserts a memory barrier into your code. This barrier guarantees that every operation that appears in the source code before the call to this routine will complete before any operation that appears after the call.

For more info about memory barriers, see [**KeMemoryBarrier**](./nf-wdm-kememorybarrier.md).

The size of the buffer must be large enough to contain at least the specified number of bytes.

Callers of <b>READ_REGISTER_BUFFER_UCHAR</b> can be running at any IRQL, assuming the <i>Buffer</i> is resident and the <i>Register</i> is resident, mapped device memory.