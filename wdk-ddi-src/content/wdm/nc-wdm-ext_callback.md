---
UID: NC:wdm.EXT_CALLBACK
title: EXT_CALLBACK (wdm.h)
description: An ExTimerCallback callback routine runs after an EX_TIMER timer object's time interval expires.
tech.root: kernel
ms.date: 01/09/2023
keywords: ["EXT_CALLBACK callback function"]
ms.keywords: EXT_CALLBACK, ExTimerCallback, ExTimerCallback routine [Kernel-Mode Driver Architecture], kernel.extimercallback, wdm/ExTimerCallback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.lib: 
req.dll: 
req.irql: Called at DISPATCH_LEVEL.
targetos: Windows
req.typenames: 
f1_keywords:
 - EXT_CALLBACK
 - wdm/EXT_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - EXT_CALLBACK
---

## -description

An *ExTimerCallback* callback routine runs after an [EX_TIMER](/windows-hardware/drivers/kernel/exxxxtimer-routines-and-ex-timer-objects) timer object's time interval expires.

## -parameters

### -param Timer [in]

A pointer to an [EX_TIMER](/windows-hardware/drivers/kernel/exxxxtimer-routines-and-ex-timer-objects) structure. This structure is a timer object that was previously allocated by the [ExAllocateTimer](./nf-wdm-exallocatetimer.md) routine.

### -param Context [in]

The context value that your driver previously supplied as the *CallbackContext* parameter of the [ExAllocateTimer](./nf-wdm-exallocatetimer.md) routine.

## -remarks

As an option, your driver can supply a pointer to an *ExTimerCallback* routine in the *Callback* parameter that your driver passes to the [ExAllocateTimer](./nf-wdm-exallocatetimer.md) routine. After the timer expires, the operating system calls the *ExTimerCallback* routine.

To start a timer operation, the driver passes the timer object as an input parameter to the [ExSetTimer](./nf-wdm-exsettimer.md) routine. After the timer expires, the operating system schedules the *ExTimerCallback* routine to run.

A timer object is a waitable object. A driver thread can call a routine such as [KeWaitForSingleObject](./nf-wdm-kewaitforsingleobject.md) or [KeWaitForMultipleObjects](./nf-wdm-kewaitformultipleobjects.md) to wait for the timer to expire. When the timer expires, the operating system signals the timer object.

A timer might be canceled before it expires. The driver can call the [ExCancelTimer](./nf-wdm-excanceltimer.md) routine to explicitly cancel a timer. If the driver calls the [ExSetTimer](./nf-wdm-exsettimer.md) routine to start a new timer on a timer object before a previously set timer on this object expires, this call implicitly cancels the previous timer and then starts the new timer.

An *ExTimerCallback* routine can call a routine such as **ExSetTimer** or [ExDeleteTimer](./nf-wdm-exdeletetimer.md). If an *ExTimerCallback* routine calls **ExDeleteTimer**, the *Wait* parameter supplied in this call must be **FALSE**. For more information, see [Deleting a System-Allocated Timer Object](/windows-hardware/drivers/kernel/deleting-a-system-allocated-timer-object).

In a multiprocessor system, *ExTimerCallback* callbacks for two successive expirations of a periodic timer might simultaneously run on two different processors.

For more information, see [ExXxxTimer Routines and EX_TIMER Objects](/windows-hardware/drivers/kernel/exxxxtimer-routines-and-ex-timer-objects).

### Examples

To define an *ExTimerCallback* callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function type helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an *ExTimerCallback* callback routine that is named `MyExTimerCallback`, use the EXT_CALLBACK function type, as shown in this code example:

```cpp
EXT_CALLBACK  MyExTimerCallback;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
VOID
  MyExTimerCallback(
    PEX_TIMER  Timer,
    PVOID  Context
    )
  {...}
```

The EXT_CALLBACK function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the EXT_CALLBACK function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For more information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

[EX_TIMER](/windows-hardware/drivers/kernel/exxxxtimer-routines-and-ex-timer-objects)

[ExAllocateTimer](./nf-wdm-exallocatetimer.md)

[ExCancelTimer](./nf-wdm-excanceltimer.md)

[ExSetTimer](./nf-wdm-exsettimer.md)

[KeWaitForMultipleObjects](./nf-wdm-kewaitformultipleobjects.md)

[KeWaitForSingleObject](./nf-wdm-kewaitforsingleobject.md)