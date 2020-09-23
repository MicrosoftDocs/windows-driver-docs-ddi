---
UID: NC:storport.HW_COMPLETE_SERVICE_IRP
title: HW_COMPLETE_SERVICE_IRP (storport.h)
description: The HwStorCompleteServiceIrp routine is called when the virtual adapter is being removed. When this happens, the Storport virtual miniport can complete any reverse-callback IRPs received in HwStorCompleteServiceIrp.
old-location: storage\hwstorcompleteserviceirp.htm
tech.root: storage
ms.assetid: 1a6a6073-27ec-43c0-b5ec-37ef4177fa54
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
 - HwStorCompleteServiceIrp
---

# HW_COMPLETE_SERVICE_IRP callback function


## -description

The <b>HwStorCompleteServiceIrp</b> routine is called when the virtual adapter is being removed. When this happens, the Storport virtual miniport can complete any reverse-callback IRPs received in <b>HwStorCompleteServiceIrp</b>.

## -parameters

### -param DeviceExtension

A pointer to the virtual miniport driver's per-adapter storage area.

## -remarks

The name <b>HwStorCompleteServiceIrp</b> is placeholder text for the actual routine name. The actual prototype of this routine is defined in Storport.h as follows:


```
typedef
VOID
HW_COMPLETE_SERVICE_IRP (
  _In_ PVOID  DeviceExtension
  );
```

The port driver calls the Storport virtual miniport driver's <b>HwStorCompleteServiceIrp</b>routine at PASSIVE_LEVEL without holding any spin locks. The virtual miniport driver completes the IRP by calling the <b>HwStorCompleteServiceIrp</b> routine.


#### Examples

To define an <b>HwStorCompleteServiceIrp</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a <b>HwStorCompleteServiceIrp</b> callback routine that is named <i>MyHwCompleteServiceIrp</i>, use the <b>HW_COMPLETE_SERVICE_IRP</b> type as shown in this code example:


```
HW_COMPLETE_SERVICE_IRP MyHwCompleteServiceIrp;
```

Then, implement your callback routine as follows:


```
_Use_decl_annotations_
VOID
MyHwCompleteServiceIrp (
  _In_ PVOID  DeviceExtension
  );
  {
      ...
  }
```

The <b>HW_COMPLETE_SERVICE_IRP</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_COMPLETE_SERVICE_IRP</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-storport-drivers">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_process_service_request">HwStorProcessServiceRequest</a>



<a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportcompleteserviceirp">StorPortCompleteServiceIrp</a>