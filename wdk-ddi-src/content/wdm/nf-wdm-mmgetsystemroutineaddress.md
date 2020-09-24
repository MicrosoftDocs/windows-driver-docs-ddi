---
UID: NF:wdm.MmGetSystemRoutineAddress
title: MmGetSystemRoutineAddress function (wdm.h)
description: The MmGetSystemRoutineAddress routine returns a pointer to a function specified by SystemRoutineName.
old-location: kernel\mmgetsystemroutineaddress.htm
tech.root: kernel
ms.assetid: 87e20abc-eb65-40c0-943e-eb194022a2de
ms.date: 04/30/2018
keywords: ["MmGetSystemRoutineAddress function"]
ms.keywords: MmGetSystemRoutineAddress, MmGetSystemRoutineAddress routine [Kernel-Mode Driver Architecture], k106_4cd56243-e8f4-428a-95f2-4e7a1d2a7396.xml, kernel.mmgetsystemroutineaddress, wdm/MmGetSystemRoutineAddress
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - MmGetSystemRoutineAddress
 - wdm/MmGetSystemRoutineAddress
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmGetSystemRoutineAddress
---

# MmGetSystemRoutineAddress function


## -description

The <b>MmGetSystemRoutineAddress</b> routine returns a pointer to a function specified by <i>SystemRoutineName</i>.

## -parameters

### -param SystemRoutineName 

[in]
Specifies the name of the system routine to resolve.

## -returns

If the function name can be resolved, the routine returns a pointer to the function. Otherwise, the routine returns <b>NULL</b>.

## -remarks

Drivers can use this routine to determine if a routine is available on a specific version of Windows. It can only be used for routines exported by the kernel or HAL, not for any driver-defined routine.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioiswdmversionavailable">IoIsWdmVersionAvailable</a>