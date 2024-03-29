---
UID: NC:storport.HW_PROCESS_SERVICE_REQUEST
title: HW_PROCESS_SERVICE_REQUEST (storport.h)
description: The HwStorProcessServiceRequest callback routine receives the device control IRP that contains the IOCTL_MINIPORT_PROCESS_SERVICE_IRP request when a caller, such as a user-mode application or kernel-mode driver, requires a &#0034;reverse callback&#0034; operation.
old-location: storage\hwstorprocessservicerequest.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["HW_PROCESS_SERVICE_REQUEST callback function"]
ms.keywords: HW_PROCESS_SERVICE_REQUEST, HwStorProcessServiceRequest, HwStorProcessServiceRequest routine [Storage Devices], storage.hwstorprocessservicerequest, storport/HwStorProcessServiceRequest, storvmini_50b0d1a2-74bf-4ee4-a9f7-3c30f1a81507.xml
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
 - HW_PROCESS_SERVICE_REQUEST
 - storport/HW_PROCESS_SERVICE_REQUEST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Storport.h
api_name:
 - HW_PROCESS_SERVICE_REQUEST
---

# HW_PROCESS_SERVICE_REQUEST callback function

## -description

The **HwStorProcessServiceRequest** callback routine receives the device control IRP that contains the  [**IOCTL_MINIPORT_PROCESS_SERVICE_IRP**](../ntddscsi/ni-ntddscsi-ioctl_miniport_process_service_irp.md) request when a caller, such as a user-mode application or kernel-mode driver, requires a "reverse callback" operation. The I/O is completed by the miniport driver when it needs to tell the caller of something or needs the caller to do something.

## -parameters

### -param DeviceExtension

A pointer to the virtual miniport driver's per-adapter storage area.

### -param Irp

A pointer to the I/O request.

## -remarks

The name **HwStorProcessServiceRequest** is placeholder text for the actual routine name. The actual prototype of this routine is defined in *Storport.h* as follows:

``` c
typedef
VOID
HW_PROCESS_SERVICE_REQUEST (
  _In_ PVOID  DeviceExtension,
  _In_ PVOID  Irp
  );
```

The port driver calls the Storport virtual miniport driver's **HwStorProcessServiceRequest** routine at PASSIVE_LEVEL. The virtual miniport driver completes the IRP by calling the [**StorPortCompleteServiceIrp**](nf-storport-storportcompleteserviceirp.md) routine.

### Examples

To define an **HwStorProcessServiceRequest** callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a **HwStorProcessServiceRequest** callback routine that is named **MyHwProcessServiceRequest**, use the **HW_PROCESS_SERVICE_REQUEST** type as shown in this code example:

``` c
HW_PROCESS_SERVICE_REQUEST MyHwProcessServiceRequest;
```

Then, implement your callback routine as follows:

``` c
_Use_decl_annotations_
VOID
MyHwProcessServiceRequest (
  _In_ PVOID  DeviceExtension,
  _In_ PVOID  Irp
  );
  {
      ...
  }
```

The **HW_PROCESS_SERVICE_REQUEST** function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the **HW_PROCESS_SERVICE_REQUEST** function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions Using Function Role Types for Storport Drivers](/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-storport-drivers). For information about _Use_decl_annotations_, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

[**IOCTL_MINIPORT_PROCESS_SERVICE_IRP**](../ntddscsi/ni-ntddscsi-ioctl_miniport_process_service_irp.md)

[**StorPortCompleteServiceIrp**](nf-storport-storportcompleteserviceirp.md)
