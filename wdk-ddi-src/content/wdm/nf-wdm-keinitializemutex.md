---
UID: NF:wdm.KeInitializeMutex
title: KeInitializeMutex function (wdm.h)
description: The KeInitializeMutex routine initializes a mutex object, setting it to a signaled state.
old-location: kernel\keinitializemutex.htm
tech.root: kernel
ms.date: 07/29/2021
keywords: ["KeInitializeMutex function"]
ms.keywords: KeInitializeMutex, KeInitializeMutex routine [Kernel-Mode Driver Architecture], k105_0e268ff3-6e9d-41ab-acfd-0bb71e973115.xml, kernel.keinitializemutex, wdm/KeInitializeMutex
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - KeInitializeMutex
 - wdm/KeInitializeMutex
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeInitializeMutex
---

# KeInitializeMutex function

## -description

The **KeInitializeMutex** routine initializes a mutex object, setting it to a signaled state.

## -parameters

### -param Mutex

[out] Pointer to a mutex object, for which the caller provides the storage. The storage must be 4-byte aligned on 32-bit platforms, and 8-byte aligned on 64-bit platforms.

### -param Level

[in] Reserved. Drivers set this to zero.

## -remarks

For better performance, use fast mutexes or guarded mutexes. For more information, see [Alternatives to Mutex Objects](/windows-hardware/drivers/kernel/alternatives-to-mutex-objects).

The mutex object is initialized with an initial state of signaled.

Storage for a mutex object must be resident: in the device extension of a driver-created device object, in the controller extension of a driver-created controller object, or in nonpaged pool allocated by the caller.

For more information about mutex objects, see [Mutex Objects](/windows-hardware/drivers/kernel/introduction-to-mutex-objects).

## -see-also

[ExInitializeFastMutex](./nf-wdm-exinitializefastmutex.md)

[KeReadStateMutex](./nf-wdm-kereadstatemutex.md)

[KeReleaseMutex](./nf-wdm-kereleasemutex.md)

[KeWaitForMultipleObjects](./nf-wdm-kewaitformultipleobjects.md)

[KeWaitForSingleObject](./nf-wdm-kewaitforsingleobject.md)