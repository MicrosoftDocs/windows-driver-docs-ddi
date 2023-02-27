---
UID: NF:wdm.KeRegisterNmiCallback
title: KeRegisterNmiCallback function (wdm.h)
description: The KeRegisterNmiCallback routine registers a routine to be called whenever a nonmaskable interrupt (NMI) occurs.
tech.root: kernel
ms.date: 01/12/2023
keywords: ["KeRegisterNmiCallback function"]
ms.keywords: KeRegisterNmiCallback, KeRegisterNmiCallback routine [Kernel-Mode Driver Architecture], k105_4abdb9bc-8548-42f3-8305-c116ce15e0a4.xml, kernel.keregisternmicallback, wdm/KeRegisterNmiCallback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlKeApcLte2, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: IRQL <= APC_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - KeRegisterNmiCallback
 - wdm/KeRegisterNmiCallback
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeRegisterNmiCallback
---

## -description

The **KeRegisterNmiCallback** routine registers a routine to be called whenever a nonmaskable interrupt (NMI) occurs.

## -parameters

### -param CallbackRoutine [in]

Pointer to a function of the form:

```cpp
BOOLEAN
 XxxNmiCallback(
 IN PVOID Context,
  IN BOOLEAN Handled
 );
```

### -param Context [in, optional]

Specifies the value to be passed as the *Context* parameter of *XxxNmiCallback* when it is called.

## -returns

On success, **KeRegisterNmiCallback** returns an opaque pointer that the caller passes to [KeDeregisterNmiCallback](./nf-wdm-kederegisternmicallback.md) to deregister the callback. The routine returns **NULL** if it is unable to register the callback.

## -remarks

When a nonmaskable interrupt occurs, the system calls each registered callback in reverse order from the order in which they were registered. For the first callback, the system passes **FALSE** as the *Handled* parameter. For each subsequent callback, if any previous callback returned **TRUE**, the system passes **TRUE** as the *Handled* parameter, otherwise it passes **FALSE**. If any callback returns a value of **TRUE**, the system considers the interrupt to have been handled. Otherwise, the system calls the HAL's default handler for the interrupt, which normally causes the system to bug check.

The callback routine must be able to be run at IRQL = HIGH_LEVEL.

## -see-also

[KeDeregisterNmiCallback](./nf-wdm-kederegisternmicallback.md)