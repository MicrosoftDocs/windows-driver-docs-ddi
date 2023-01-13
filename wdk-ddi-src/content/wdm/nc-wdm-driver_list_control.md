---
UID: NC:wdm.DRIVER_LIST_CONTROL
title: DRIVER_LIST_CONTROL (wdm.h)
description: The AdapterListControl routine starts a direct memory access (DMA) scatter/gather operation.
tech.root: kernel
ms.date: 01/09/2023
keywords: ["DRIVER_LIST_CONTROL callback function"]
ms.keywords: AdapterListControl, AdapterListControl routine [Kernel-Mode Driver Architecture], DRIVER_LIST_CONTROL, DrvrRtns_feb5903f-df38-4471-ab1e-2e6341620774.xml, kernel.adapterlistcontrol, wdm/AdapterListControl
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
req.irql: Called at DISPATCH_LEVEL.
targetos: Windows
req.typenames: 
f1_keywords:
 - DRIVER_LIST_CONTROL
 - wdm/DRIVER_LIST_CONTROL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - DRIVER_LIST_CONTROL
---

## -description

The *AdapterListControl* routine starts a direct memory access (DMA) scatter/gather operation.

## -parameters

### -param DeviceObject [in]

Caller-supplied pointer to a [DEVICE_OBJECT](/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object) structure. This is the device object for the target device, previously created by the driver's [AddDevice](/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device) routine.

### -param Irp [in]

Caller-supplied pointer to an [IRP](/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp) structure that describes the I/O operation, if the driver has a [StartIo](/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_startio) routine. Otherwise, not used.

### -param ScatterGather [in]

Caller-supplied pointer to a [SCATTER_GATHER_LIST](/windows-hardware/drivers/ddi/wdm/ns-wdm-_scatter_gather_list) structure describing scatter/gather regions.

### -param Context [in]

Caller-supplied pointer to driver-defined context information, specified in a previous call to [AllocateAdapterChannel](/windows-hardware/drivers/ddi/wdm/nc-wdm-pallocate_adapter_channel).

## -remarks

To register an *AdapterListControl* routine for a specific device object, a driver must call [IoGetDmaAdapter](/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter) to obtain an adapter object, then call [GetScatterGatherList](/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_scatter_gather_list) to request use of the adapter and to supply the *AdapterListControl* routine's address. When the adapter is free, the system calls the *AdapterListControl* routine.

### Examples

To define an *AdapterListControl* callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an *AdapterListControl* callback routine that is named `MyAdapterListControl`, use the DRIVER_LIST_CONTROL type as shown in this code example:

```cpp
DRIVER_LIST_CONTROL MyAdapterListControl;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
VOID
  MyAdapterListControl(
    struct _DEVICE_OBJECT  *DeviceObject,
    struct _IRP  *Irp,
    PSCATTER_GATHER_LIST  ScatterGather,
    PVOID  Context
    )
  {
      // Function body
  }
```

The DRIVER_LIST_CONTROL function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the DRIVER_LIST_CONTROL function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

For detailed information about implementing an *AdapterListControl* routine, see [Using Scatter/Gather DMA](/windows-hardware/drivers/kernel/using-scatter-gather-dma).
