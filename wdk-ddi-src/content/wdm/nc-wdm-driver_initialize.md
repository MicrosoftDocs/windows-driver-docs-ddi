---
UID: NC:wdm.DRIVER_INITIALIZE
title: DRIVER_INITIALIZE (wdm.h)
description: DriverEntry is the first routine called after a driver is loaded, and is responsible for initializing the driver.
tech.root: kernel
ms.date: 01/09/2023
keywords: ["DRIVER_INITIALIZE callback function"]
ms.keywords: DRIVER_INITIALIZE, DriverEntry, DriverEntry routine [Kernel-Mode Driver Architecture], DrvrRtns_dc503a23-7c31-421d-ac7b-ff6f4651e44e.xml, kernel.driverentry, wdm/DriverEntry
req.header: wdm.h
req.include-header: Mcd.h, Ntddk.h, Ntifs.h, Wudfwdm.h
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
 - DRIVER_INITIALIZE
 - wdm/DRIVER_INITIALIZE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - DRIVER_INITIALIZE
---

## -description

**DriverEntry** is the first routine called after a driver is loaded, and is responsible for initializing the driver.

## -parameters

### -param DriverObject [in]

A pointer to a [**DRIVER_OBJECT**](./ns-wdm-_driver_object.md) structure. This is the driver's driver object.

### -param RegistryPath [in]

A pointer to a counted Unicode string specifying the path to the driver's registry key.

## -returns

If the routine succeeds, it must return STATUS_SUCCESS. Otherwise, it must return one of the error status values defined in Ntstatus.h.

## -remarks

The *DriverObject* parameter supplies the **DriverEntry** routine with a pointer to the driver's driver object, which is allocated by the I/O manager. The **DriverEntry** routine must fill in the driver object with entry points for the driver's standard routines.

The *DriverObject* pointer gives the driver access to *DriverObject-*>**HardwareDatabase**, which points to a counted Unicode string that specifies a path to the registry's **\Registry\Machine\Hardware** tree.

The registry path string pointed to by *RegistryPath* is of the form **\Registry\Machine\System\CurrentControlSet\Services\\*DriverName***. A driver can use this path to store driver-specific information; see [Registry Keys for Drivers](/windows-hardware/drivers/install/overview-of-registry-trees-and-keys). The **DriverEntry** routine should save a copy of the Unicode string, not the pointer, since the I/O manager frees the *RegistryPath* buffer after **DriverEntry** returns.

For more information about implementing a **DriverEntry** routine, see [Writing a DriverEntry Routine](/windows-hardware/drivers/kernel/writing-a-driverentry-routine).

While it is possible to name this routine something other than **DriverEntry**, doing so is not recommended. The DDK-supplied build tools automatically inform the linker that the driver's entry point is called **DriverEntry**, so giving the routine another name requires you to modify the build tools. For more information about build tools, see [Building a Driver](/windows-hardware/drivers/develop/building-a-driver).

### Examples

To define a **DriverEntry** callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

To define a **DriverEntry** callback routine, use the DRIVER_INITIALIZE type as shown in this code example:

```cpp
DRIVER_INITIALIZE DriverEntry;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
NTSTATUS 
  DriverEntry( 
    struct _DRIVER_OBJECT  *DriverObject,
    PUNICODE_STRING  RegistryPath 
    )
  {
      // Function body
  }
```

The DRIVER_INITIALIZE function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the DRIVER_INITIALIZE function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

[**DRIVER_OBJECT**](./ns-wdm-_driver_object.md)