---
UID: NF:wdm.MmGetSystemRoutineAddressEx
title: MmGetSystemRoutineAddressEx function
author: windows-driver-content
description: TBD
tech.root: kernel
ms.assetid: a02b0193-1f21-497b-9628-6ea6afb43d50
ms.author: windowsdriverdev
ms.date: 03/01/2020
ms.topic: function
ms.keywords: MmGetSystemRoutineAddressEx
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type:
- DllExport
api_location: 
- wdm.h
api_name: 
- MmGetSystemRoutineAddressEx
product: 
- Windows
targetos: Windows

---

# MmGetSystemRoutineAddressEx function


## -description

This function returns the address of the specified function in the specified system module.

## -parameters

### -param ModuleName

Supplies a pointer to a UNICODE_STRING that describes the system module.

### -param FunctionName

Supplies a pointer to the name of the desired function.


## -returns

If the specified module is not in the loaded module list, the specified loaded module is the kernel or the HAL, or the specified function cannot be located, then NULL is returned. Otherwise, the appropriate bit is set in the CFG bitmap and a pointer to the specified function is returned.

## -remarks

## -see-also