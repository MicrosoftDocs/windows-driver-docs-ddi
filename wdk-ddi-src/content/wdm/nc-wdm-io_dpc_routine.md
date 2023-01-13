---
UID: NC:wdm.IO_DPC_ROUTINE
title: IO_DPC_ROUTINE (wdm.h)
description: The DpcForIsr routine finishes the servicing of an I/O operation, after an InterruptService routine returns.
tech.root: kernel
ms.date: 01/09/2023
keywords: ["IO_DPC_ROUTINE callback function"]
ms.keywords: DpcForIsr, DpcForIsr routine [Kernel-Mode Driver Architecture], DrvrRtns_2d3825cf-0f9b-4698-9deb-e9fe5757fb9c.xml, IO_DPC_ROUTINE, kernel.dpcforisr, wdm/DpcForIsr
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
 - IO_DPC_ROUTINE
 - wdm/IO_DPC_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - IO_DPC_ROUTINE
---

## -description

The *DpcForIsr* routine finishes the servicing of an I/O operation, after an [InterruptService](/windows-hardware/drivers/ddi/wdm/nc-wdm-kservice_routine) routine returns.

## -parameters

### -param Dpc [in]

Caller-supplied pointer to a [KDPC](/windows-hardware/drivers/kernel/eprocess) structure, which represents the DPC object that is associated with this *DpcForIsr* routine.

### -param DeviceObject [in]

Caller-supplied pointer to a [DEVICE_OBJECT](/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object) structure. This is the device object for the target device, previously created by the driver's [AddDevice](/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device) routine.

### -param Irp [in, out]

Caller-supplied pointer to an [IRP](/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp) structure that describes the I/O operation.

### -param Context [in, optional]

Caller-supplied pointer to driver-defined context information, specified in a previous call to [IoRequestDpc](/windows-hardware/drivers/ddi/wdm/nf-wdm-iorequestdpc).

## -remarks

To register a *DpcForIsr* routine for a specific device object, a driver must call [IoInitializeDpcRequest](/windows-hardware/drivers/ddi/wdm/nf-wdm-ioinitializedpcrequest), which causes the system to allocate and initialize one DPC object. (If you need multiple DPC routines, use [CustomDpc](/windows-hardware/drivers/ddi/wdm/nc-wdm-kdeferred_routine) routines.)

To queue a *DpcForIsr* routine for execution, a driver's [InterruptService](/windows-hardware/drivers/ddi/wdm/nc-wdm-kservice_routine) routine must call [IoRequestDPC](/windows-hardware/drivers/ddi/wdm/nf-wdm-iorequestdpc).

A *DpcForIsr* routine is typically responsible for at least the following tasks:

- Completing the I/O operation described by the received IRP.

- Dequeuing next IRP.

  If the driver uses the system-supplied IRP queue, the *DpcForIsr* routine should call [IoStartNextPacket](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iostartnextpacket) or [IoStartNextPacketByKey](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iostartnextpacketbykey), so the driver's [StartIo](/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_startio) routine will start processing the next I/O request.

  If the driver uses internal IRP queues, the *DpcForIsr* routine should dequeue the next IRP and begin processing for the next I/O request.

- Setting the I/O status block in the received IRP and calling [IoCompleteRequest](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocompleterequest) for the completed request.

A *DpcForIsr* routine might also retry a failed operation or set up the next transfer for a large I/O request that has been broken into smaller pieces.

For more information about *DpcForIsr* routines, see [DPC Objects and DPCs](/windows-hardware/drivers/kernel/dpc-objects-and-dpcs).

### Examples

To define a *DpcForIsr* callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a *DpcForIsr* callback routine that is named `MyDpcForIsr`, use the IO_DPC_ROUTINE type as shown in this code example:

```cpp
IO_DPC_ROUTINE MyDpcForIsr;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
VOID
  MyDpcForIsr(
    PKDPC  Dpc,
    struct _DEVICE_OBJECT  *DeviceObject,
    struct _IRP  *Irp,
    PVOID  Context
    )
  {
      // Function body
  }
```

The IO_DPC_ROUTINE function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the IO_DPC_ROUTINE function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).
