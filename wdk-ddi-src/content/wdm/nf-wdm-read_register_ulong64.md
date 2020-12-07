---
UID: NF:wdm.READ_REGISTER_ULONG64
title: READ_REGISTER_ULONG64 function (wdm.h)
description: The READ_REGISTER_ULONG64 function reads a ULONG64 value from the specified register address.
tech.root: kernel
ms.date: 09/15/2020
keywords: ["READ_REGISTER_ULONG64 function"]
ms.keywords: READ_REGISTER_ULONG64, READ_REGISTER_ULONG64 function
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
 - READ_REGISTER_ULONG64
 - wdm/READ_REGISTER_ULONG64
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - READ_REGISTER_ULONG64
---

# READ_REGISTER_ULONG64 function (wdm.h)


## -description


The <b>READ_REGISTER_ULONG64</b> macro reads a ULONG64 value from the specified register address.

## -parameters

### -param Register 

[in]
Pointer to the register address, which must be a mapped range in memory space.

## -returns

**READ_REGISTER_ULONG64** returns the ULONG64 value that is read from the specified register address.

## -remarks

Callers of the **READ_REGISTER_ULONG64** macro can be running at any IRQL, assuming the *Register* address is resident, mapped device memory. 
