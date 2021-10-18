---
UID: NC:storport.HW_COMPLETE_SERVICE_IRP
title: HW_COMPLETE_SERVICE_IRP (storport.h)
description: The HwStorCompleteServiceIrp routine is called when the virtual adapter is being removed. When this happens, the Storport virtual miniport can complete any reverse-callback IRPs received in HwStorCompleteServiceIrp.
old-location: storage\hwstorcompleteserviceirp.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["HW_COMPLETE_SERVICE_IRP callback function"]
ms.keywords: HW_COMPLETE_SERVICE_IRP, HwStorCompleteServiceIrp, HwStorCompleteServiceIrp routine [Storage Devices], storage.hwstorcompleteserviceirp, storport/HwStorCompleteServiceIrp, storvmini_57cddd18-134c-4ecc-9180-4c4b3ff3903d.xml
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - HW_COMPLETE_SERVICE_IRP
 - storport/HW_COMPLETE_SERVICE_IRP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Storport.h
api_name:
 - HW_COMPLETE_SERVICE_IRP
---

# HW_COMPLETE_SERVICE_IRP callback function

## -description

The **HwStorCompleteServiceIrp** routine is called when the virtual adapter is being removed. When this happens, the Storport virtual miniport can complete any reverse-callback IRPs received in **HwStorCompleteServiceIrp**.

## -parameters

### -param DeviceExtension

A pointer to the virtual miniport driver's per-adapter storage area.

## -remarks

The name **HwStorCompleteServiceIrp** is placeholder text for the actual routine name. The actual prototype of this routine is defined in Storport.h as follows:

``` c
typedef
VOID
HW_COMPLETE_SERVICE_IRP (
  _In_ PVOID  DeviceExtension
  );
```

The port driver calls the Storport virtual miniport driver's **HwStorCompleteServiceIrp**routine at PASSIVE_LEVEL without holding any spin locks. The virtual miniport driver completes the IRP by calling the **HwStorCompleteServiceIrp** routine.

### Examples

To define an **HwStorCompleteServiceIrp** callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a **HwStorCompleteServiceIrp** callback routine that is named *&**MyHwCompleteServiceIrp**, use the **HW_COMPLETE_SERVICE_IRP** type as shown in this code example:

``` c
HW_COMPLETE_SERVICE_IRP MyHwCompleteServiceIrp;
```

Then, implement your callback routine as follows:

``` c
_Use_decl_annotations_
VOID
MyHwCompleteServiceIrp (
  _In_ PVOID  DeviceExtension
  );
  {
      ...
  }
```

The **HW_COMPLETE_SERVICE_IRP** function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the **HW_COMPLETE_SERVICE_IRP** function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions Using Function Role Types for Storport Drivers](/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-storport-drivers). For information about _Use_decl_annotations_, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

[**HwStorProcessServiceRequest**](nc-storport-hw_process_service_request.md)

[**StorPortCompleteServiceIrp**](nf-storport-storportcompleteserviceirp.md)
