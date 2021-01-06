---
UID: NF:wdm.READ_REGISTER_ULONG
title: READ_REGISTER_ULONG function (wdm.h)
description: The READ_REGISTER_ULONG routine reads a ULONG value from the specified register address.
old-location: kernel\read_register_ulong.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["READ_REGISTER_ULONG function"]
ms.keywords: READ_REGISTER_ULONG, READ_REGISTER_ULONG routine [Kernel-Mode Driver Architecture], k103_c2da9866-18ac-438b-aa32-991d1bda139f.xml, kernel.read_register_ulong, wdm/READ_REGISTER_ULONG
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
 - READ_REGISTER_ULONG
 - wdm/READ_REGISTER_ULONG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - READ_REGISTER_ULONG
---

# READ_REGISTER_ULONG function (wdm.h)


## -description

The <b>READ_REGISTER_ULONG</b> routine reads a ULONG value from the specified register address.

## -parameters

#### - Register [in]

Pointer to the register address, which must be a mapped range in memory space.

## -returns

<b>READ_REGISTER_ULONG</b> returns the ULONG value read from the specified register address.

## -remarks

Callers of <b>READ_REGISTER_ULONG</b> can be running at any IRQL, assuming the <i>Register</i> is resident, mapped device memory.

