---
UID: NC:storport.HW_PASSIVE_INITIALIZE_ROUTINE
title: HW_PASSIVE_INITIALIZE_ROUTINE (storport.h)
description: The HwStorPassiveInitializeRoutine callback routine is called after the HwStorInitialize routine when the current IRQL is at PASSIVE_LEVEL.
old-location: storage\hwstorpassiveinitializeroutine.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["HW_PASSIVE_INITIALIZE_ROUTINE callback function"]
ms.keywords: HW_PASSIVE_INITIALIZE_ROUTINE, HwStorPassiveInitializeRoutine, HwStorPassiveInitializeRoutine routine [Storage Devices], storage.hwstorpassiveinitializeroutine, stormini_e2404f14-1cdc-44d7-bd58-97acfa57bc36.xml, storport/HwStorPassiveInitializeRoutine
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
req.irql: PASSIVE_LEVEL (See Remarks section.)
targetos: Windows
req.typenames: 
f1_keywords:
 - HW_PASSIVE_INITIALIZE_ROUTINE
 - storport/HW_PASSIVE_INITIALIZE_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Storport.h
api_name:
 - HW_PASSIVE_INITIALIZE_ROUTINE
---

# HW_PASSIVE_INITIALIZE_ROUTINE callback function

## -description

The **HwStorPassiveInitializeRoutine** callback routine is called after the [**HwStorInitialize**](nc-storport-hw_initialize.md) routine when the current IRQL is at PASSIVE_LEVEL. The **HwStorPassiveInitializeRoutine** callback is set by calling the [**StorPortEnablePassiveInitialization**](nf-storport-storportenablepassiveinitialization.md) routine. Initializing of the miniport's deferred procedure calls (DPCs) occurs in the **HwStorPassiveInitializeRoutine** callback.

## -parameters

### -param DeviceExtension

#### - HwDeviceExtension

A pointer to a per-adapter storage area.

## -returns

The **HwStorPassiveInitializeRoutine** routine returns **TRUE** if the miniport successfully initialized the processing of DPCs, or **FALSE** if the initialization process failed.

## -remarks

The **HwStorPassiveInitializeRoutine** routine should initialize any DPCs that the miniport driver will use. The port driver calls **HwStorPassiveInitializeRoutine** at PASSIVE_LEVEL without any spin locks held. Interrupts are enabled while this routine is called.

The name **HwStorPassiveInitializeRoutine** is just a placeholder. The actual prototype for this callback routine is defined in *Storport.h* as follows:

``` c
typedef
BOOLEAN
(*PHW_PASSIVE_INITIALIZE_ROUTINE) (
  _In_ PVOID DeviceExtension
  );
```

The port driver calls the **HwStorPassiveInitializeRoutine** routine at PASSIVE IRQL without acquiring any spin locks.

### Examples

To define an **HwStorPassiveInitializeRoutine** callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a **HwStorPassiveInitializeRoutine** callback routine that is named **MyHwPassiveInitialize**, use the **HW_PASSIVE_INITIALIZE_ROUTINE** type as shown in this code example:

``` c
HW_PASSIVE_INITIALIZE_ROUTINE MyHwPassiveInitialize;
```

Then, implement your callback routine as follows:

``` c
_Use_decl_annotations_
BOOLEAN
MyHwPassiveInitialize (
  _In_ PVOID  DeviceExtension
  );
  {
      ...
  }
```

The **HW_PASSIVE_INITIALIZE_ROUTINE** function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the **HW_PASSIVE_INITIALIZE_ROUTINE** function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions Using Function Role Types for Storport Drivers](/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-storport-drivers). For information about _Use_decl_annotations_, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

[**HwStorInitialize**](nc-storport-hw_initialize.md)

[**StorPortEnablePassiveInitialization**](nf-storport-storportenablepassiveinitialization.md)
