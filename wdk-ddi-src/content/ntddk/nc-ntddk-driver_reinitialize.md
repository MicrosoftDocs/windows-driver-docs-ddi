---
UID: NC:ntddk.DRIVER_REINITIALIZE
title: DRIVER_REINITIALIZE (ntddk.h)
description: The Reinitialize routine continues driver and device initialization after the driver's DriverEntry routine returns.
tech.root: kernel
ms.date: 01/09/2023
keywords: ["DRIVER_REINITIALIZE callback function"]
ms.keywords: DRIVER_REINITIALIZE, DrvrRtns_193becfd-0e72-48f0-b6da-b916851c31a4.xml, Reinitialize, Reinitialize routine [Kernel-Mode Driver Architecture], kernel.reinitialize, ntddk/Reinitialize
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.irql: Called at PASSIVE_LEVEL.
targetos: Windows
req.typenames: 
f1_keywords:
 - DRIVER_REINITIALIZE
 - ntddk/DRIVER_REINITIALIZE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ntddk.h
api_name:
 - DRIVER_REINITIALIZE
---

## -description

The *Reinitialize* routine continues driver and device initialization after the driver's **DriverEntry** routine returns.

## -parameters

### -param DriverObject [in]

Caller-supplied pointer to a [DRIVER_OBJECT](/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object) structure. This is the driver's driver object.

### -param Context [in, optional]

Caller-supplied pointer to context information, specified in a previous call to [IoRegisterDriverReinitialization](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioregisterdriverreinitialization) or [IoRegisterBootDriverReinitialization](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioregisterbootdriverreinitialization).

### -param Count [in]

Caller-supplied value representing the number of times the *Reinitialize* routine has been called, including the current call.

## -remarks

To queue a *Reinitialize* routine for execution, a driver's [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine must call either [IoRegisterDriverReinitialization](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioregisterdriverreinitialization) or [IoRegisterBootDriverReinitialization](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioregisterbootdriverreinitialization). The *Reinitialize* routine can also call **IoRegisterDriverReinitialization** itself, which causes the routine to be requeued. This requeuing can occur multiple times, and the routine's *Count* parameter indicates the number of times it has been called. The first call to **IoRegisterDriverReinitialization** must be made from **DriverEntry**, and **DriverEntry** must return STATUS_SUCCESS.

For more information about implementing a *Reinitialize* routine, see [Writing a Reinitialize Routine](/windows-hardware/drivers/kernel/writing-a-reinitialize-routine).

### Examples

To define a *Reinitialize* callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a *Reinitialize* callback routine that is named `MyReinitialize`, use the DRIVER_REINITIALIZE type as shown in this code example:

```cpp
DRIVER_REINITIALIZE MyReinitialize;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
VOID
  MyReinitialize(
    struct _DRIVER_OBJECT  *DriverObject,
    PVOID  Context,
    ULONG  Count
    )
  {
      // Function body
  }

```

The DRIVER_REINITIALIZE function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the DRIVER_REINITIALIZE function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).
