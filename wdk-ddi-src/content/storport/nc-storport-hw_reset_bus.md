---
UID: NC:storport.HW_RESET_BUS
title: HW_RESET_BUS (storport.h)
description: The HwStorResetBus routine is called by the port driver to clear error conditions.
old-location: storage\hwstorresetbus.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["HW_RESET_BUS callback function"]
ms.keywords: HW_RESET_BUS, HwStorResetBus, HwStorResetBus routine [Storage Devices], storage.hwstorresetbus, stormini_b3051379-4caa-4502-9492-a21672cfbf0d.xml, storport/HwStorResetBus
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.irql: DISPATCH_LEVEL (See Remarks section.)
targetos: Windows
req.typenames: 
f1_keywords:
 - HW_RESET_BUS
 - storport/HW_RESET_BUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Storport.h
api_name:
 - HW_RESET_BUS
---

# HW_RESET_BUS callback function

## -description

The **HwStorResetBus** routine is called by the port driver to clear error conditions.

## -parameters

### -param DeviceExtension

A pointer to the miniport driver's per HBA storage area.

### -param PathId

Identifies the SCSI bus to be reset.

## -returns

If the bus is successfully reset, **HwStorResetBus** returns **TRUE**.

## -remarks

The name **HwStorResetBus** is just a placeholder. The actual prototype of this routine is defined in *Storport.h* as follows:

``` c
typedef
BOOLEAN
HW_RESET_BUS (
  _In_ PVOID  DeviceExtension,
  _In ULONG  PathId
  );
```

The port driver pauses all device IO queues for the adapter and then calls the **HwStorResetBus** routine at IRQL DISPATCH_LEVEL after acquiring the StartIo spin lock.  A miniport driver is responsible for completing SRBs received by [**HwStorStartIo**](nc-storport-hw_startio.md) for **PathId** during this routine and setting their status to SRB_STATUS_BUS_RESET if necessary.

In addition to the StartIo spin lock being taken and subsequently released after **HwStorResetBus** returns, if the miniport has requested multiple channel support through PERF_CONFIGURATION_DATA, all channel tokens will be taken and, on return of the callback, released.  This ensures that no IO’s are dispatched to [**HwStorStartIo**](nc-storport-hw_startio.md) during the reset bus phase.

### Examples

To define an **HwStorResetBus** callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a **HwStorResetBus** callback routine that is named **MyHwResetBus**, use the **HW_RESET_BUS** type as shown in this code example:

``` c
HW_RESET_BUS MyHwResetBus;
```

Then, implement your callback routine as follows:

``` c
_Use_decl_annotations_
BOOLEAN
MyHwResetBus (
  _In_ PVOID  DeviceExtension,
  _In_ ULONG  PahtId
  );
  {
      ...
  }
```

The **HW_RESET_BUS** function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the **HW_RESET_BUS** function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions Using Function Role Types for Storport Drivers](/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-storport-drivers). For information about _Use_decl_annotations_, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).
