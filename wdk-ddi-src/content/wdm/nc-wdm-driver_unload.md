---
UID: NC:wdm.DRIVER_UNLOAD
title: DRIVER_UNLOAD (wdm.h)
description: The Unload routine performs any operations that are necessary before the system unloads the driver.
old-location: kernel\unload.htm
tech.root: kernel
ms.date: 04/30/2018
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

# DRIVER_UNLOAD callback function


## -description

The <i>Unload</i> routine performs any operations that are necessary before the system unloads the driver.

## -parameters

### -param DriverObject 

[in]
Caller-supplied pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a> structure. This is the driver's driver object.

## -remarks

A driver's <i>Unload</i> routine executes in a system thread context at IRQL = PASSIVE_LEVEL.

The <i>Unload</i> routine is required for WDM drivers and optional for non-WDM drivers. A driver's <i>Unload</i> routine, if supplied, should be named <i>Xxx</i><b>Unload</b>, where <i>Xxx</i> is a driver-specific prefix. The driver's <a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine must store the <i>Unload</i> routine's address in <b>DriverObject->DriverUnload</b>. (If no routine is supplied, this pointer must be <b>NULL</b>.)

For detailed information about implementing a driver's <i>Unload</i> routine, see <a href="/windows-hardware/drivers/kernel/writing-an-unload-routine">Writing an Unload Routine</a>.


#### Examples

To define an <i>Unload</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>Unload</i> callback routine that is named <code>MyUnload</code>, use the DRIVER_UNLOAD type as shown in this code example:


```
DRIVER_UNLOAD MyUnload;
```

Then, implement your callback routine as follows:


```
_Use_decl_annotations_
VOID 
  MyUnload(
    struct _DRIVER_OBJECT  *DriverObject
    )
  {
      // Function body
  }
```

The DRIVER_UNLOAD function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the DRIVER_UNLOAD function type in the header file are used. For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

<div class="code"></div>

