---
UID: NF:ioaccess.WRITE_REGISTER_ULONG~r2
title: WRITE_REGISTER_ULONG function (ioaccess.h)
description: The WRITE_REGISTER_ULONG routine writes a ULONG value to the specified address.
old-location: kernel\write_register_ulong.htm
tech.root: kernel
ms.date: 03/01/2018
keywords: ["WRITE_REGISTER_ULONG function"]
ms.keywords: WRITE_REGISTER_ULONG, WRITE_REGISTER_ULONG routine [Kernel-Mode Driver Architecture], k103_af58a3ec-4102-4a89-9c58-e56f99d793d0.xml, kernel.write_register_ulong, wdm/WRITE_REGISTER_ULONG
req.header: ioaccess.h
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
req.typenames: IDD_DRIVER_GLOBALS, *PIDD_DRIVER_GLOBALS, IDD_DRIVER_GLOBALS, *PIDD_DRIVER_GLOBALS
f1_keywords:
 - WRITE_REGISTER_ULONG
 - ioaccess/WRITE_REGISTER_ULONG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - WRITE_REGISTER_ULONG
---

# WRITE_REGISTER_ULONG function


## -description

The <b>WRITE_REGISTER_ULONG</b> routine writes a ULONG value to the specified address.

## -parameters

### -param Register 

[in]
Pointer to the register which must be a mapped range in memory space.

### -param Value 

[in]
Specifies a ULONG value to be written to the register.

## -syntax

```cpp
VOID WRITE_REGISTER_ULONG(
  _In_ PULONG Register,
  _In_ ULONG  Value
);
```

## -remarks

Callers of <b>WRITE_REGISTER_ULONG</b> can be running at any IRQL, assuming the <i>Register</i> is resident, mapped device memory.

