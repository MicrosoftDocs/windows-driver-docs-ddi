---
UID: NC:storport.HW_INTERRUPT
title: HW_INTERRUPT (storport.h)
description: The Storport driver calls the HwStorInterrupt routine after the HBA generates an interrupt request.
old-location: storage\hwstorinterrupt.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["HW_INTERRUPT callback function"]
ms.keywords: HW_INTERRUPT, HwStorInterrupt, HwStorInterrupt routine [Storage Devices], storage.hwstorinterrupt, stormini_17f68641-1cfd-47b3-a52f-be98f96e693f.xml, storport/HwStorInterrupt
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
req.irql: DIRQL
targetos: Windows
req.typenames: 
f1_keywords:
 - HW_INTERRUPT
 - storport/HW_INTERRUPT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Storport.h
api_name:
 - HW_INTERRUPT
---

# HW_INTERRUPT callback function

## -description

The Storport driver calls the **HwStorInterrupt** routine after the HBA generates an interrupt request.

## -parameters

### -param DeviceExtension

A pointer to the miniport driver's per HBA storage area.

## -returns

If the miniport driver finds that its HBA did not generate the interrupt, **HwStorInterrupt** should return **FALSE** as soon as possible. The **HwStorInterrupt** routine should return within 50 microseconds.

## -remarks

The name **HwStorInterrupt** is just a placeholder. The actual prototype of this routine is defined in *Storport.h* as follows:

``` c
typedef
BOOLEAN
HW_INTERRUPT (
  IN PVOID  DeviceExtension
  );

```

The **HwStorInterrupt** routine should return within 50 microseconds, ideally as short a time as possible. Therefore, all activity does not have to occur at high IRQL should be deferred to the [**HwStorDpcRoutine**](nc-storport-hw_dpc_routine.md that is defined in the miniport driver and issued by using [**StorPortIssueDpc**](nf-storport-storportissuedpc.md).  The latency of the DPC is very low, and it will be called immediately after the return from high IRQL.

The port driver calls the **HwStorInterrupt** routine at DIRQL.

### Examples

To define an **HwStorInterrupt** callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a **HwStorInterrupt** callback routine that is named **MyHwInterrupt**, use the **HW_INTERRUPT** type as shown in this code example:

``` c
HW_INTERRUPT MyHwInterrupt;
```

Then, implement your callback routine as follows:

``` c
_Use_decl_annotations_
BOOLEAN
MyHwInterrupt (
  _In_ PVOID  DeviceExtension
  );
  {
      ...
  }
```

The **HW_INTERRUPT** function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the **HW_INTERRUPT** function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions Using Function Role Types for Storport Drivers](/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-storport-drivers). For information about _Use_decl_annotations_, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

[**HwStorDpcRoutine**](nc-storport-hw_dpc_routine.md

[**StorPortIssueDpc**](nf-storport-storportissuedpc.md)
