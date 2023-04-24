---
UID: NC:wdm.DRIVER_UNLOAD
title: DRIVER_UNLOAD (wdm.h)
description: The Unload routine performs any operations that are necessary before the system unloads the driver.
tech.root: kernel
ms.date: 01/09/2023
keywords: ["DRIVER_UNLOAD callback function"]
ms.keywords: DRIVER_UNLOAD, DrvrRtns_68cde0dd-4521-4771-8965-309dedd87d37.xml, Unload, Unload routine [Kernel-Mode Driver Architecture], kernel.unload, wdm/Unload
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
 - DRIVER_UNLOAD
 - wdm/DRIVER_UNLOAD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - DRIVER_UNLOAD
---

## -description

The *Unload* routine performs any operations that are necessary before the system unloads the driver.

## -parameters

### -param DriverObject [in]

Caller-supplied pointer to a [DRIVER_OBJECT](./ns-wdm-_driver_object.md) structure. This is the driver's driver object.

## -remarks

A driver's *Unload* routine executes in a system thread context at IRQL = PASSIVE_LEVEL.

The *Unload* routine is required for WDM drivers and optional for non-WDM drivers. A driver's *Unload* routine, if supplied, should be named *Xxx***Unload**, where *Xxx* is a driver-specific prefix. The driver's [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine must store the *Unload* routine's address in **DriverObject->DriverUnload**. (If no routine is supplied, this pointer must be **NULL**.)

For detailed information about implementing a driver's *Unload* routine, see [Writing an Unload Routine](/windows-hardware/drivers/kernel/writing-an-unload-routine).

### Examples

To define an *Unload* callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an *Unload* callback routine that is named `MyUnload`, use the DRIVER_UNLOAD type as shown in this code example:

```cpp
DRIVER_UNLOAD MyUnload;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
VOID 
  MyUnload(
    struct _DRIVER_OBJECT  *DriverObject
    )
  {
      // Function body
  }
```

The DRIVER_UNLOAD function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the DRIVER_UNLOAD function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).