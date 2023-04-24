---
UID: NC:wdm.REQUEST_POWER_COMPLETE
title: REQUEST_POWER_COMPLETE (wdm.h)
description: The PowerCompletion callback routine completes the processing of a power IRP.
tech.root: kernel
ms.date: 01/10/2023
keywords: ["REQUEST_POWER_COMPLETE callback function"]
ms.keywords: PowerCompletion, PowerCompletion routine [Kernel-Mode Driver Architecture], REQUEST_POWER_COMPLETE, kernel.powercompletion, wdm/PowerCompletion
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
req.irql: Called at IRQL <= DISPATCH_LEVEL (see Remarks section).
targetos: Windows
req.typenames: 
f1_keywords:
 - REQUEST_POWER_COMPLETE
 - wdm/REQUEST_POWER_COMPLETE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - REQUEST_POWER_COMPLETE
---

## -description

The *PowerCompletion* callback routine completes the processing of a power IRP.

## -parameters

### -param DeviceObject [in]

A pointer to the target [DEVICE_OBJECT](./ns-wdm-_device_object.md) for the completed power IRP.

### -param MinorFunction [in]

Specifies the minor function code in the power IRP. For more information, see the list of supported **IRP_MN_*XXX*** codes in the Remarks section.

### -param PowerState [in]

Specifies the [device power state](/windows-hardware/drivers/kernel/device-power-states) or [system power state](/windows-hardware/drivers/kernel/system-power-states) that was passed to the [PoRequestPowerIrp](./nf-wdm-porequestpowerirp.md) routine.

### -param Context [in, optional]

A pointer to the context that was passed to **PoRequestPowerIrp**.

### -param IoStatus [in]

A pointer to the [IO_STATUS_BLOCK](./ns-wdm-_io_status_block.md) structure for the completed IRP.

## -remarks

A driver that sends a power IRP might need to perform additional tasks after all other drivers have completed the IRP. If so, the sending driver should register a *PowerCompletion* callback routine during the call to the [PoRequestPowerIrp](./nf-wdm-porequestpowerirp.md) routine that allocates the IRP.

A driver's *PowerCompletion* callback routine is used only for [IRP_MJ_POWER](/windows-hardware/drivers/kernel/irp-mj-power) IRPs that have minor IRP codes of [IRP_MN_SET_POWER](/windows-hardware/drivers/kernel/irp-mn-set-power), [IRP_MN_QUERY_POWER](/windows-hardware/drivers/kernel/irp-mn-query-power), and [IRP_MN_WAIT_WAKE](/windows-hardware/drivers/kernel/irp-mn-wait-wake). For more information, see [Sending IRP_MN_QUERY_POWER or IRP_MN_SET_POWER for Device Power States](/windows-hardware/drivers/kernel/sending-irp-mn-query-power-or-irp-mn-set-power-for-device-power-states) and [Wait/Wake Callback Routines](/windows-hardware/drivers/kernel/wait-wake-callback-routines).

The I/O manager calls the sending driver's *PowerCompletion* routine only after the I/O manager has called all the [IoCompletion](./nc-wdm-io_completion_routine.md) routines that were set by other drivers as they passed the IRP down the stack. The *PowerCompletion* routine performs any additional tasks that the sender of the IRP requires after all other drivers have completed the IRP. The *PowerCompletion* routine should not free the IRP—the power manager does that.

The *PowerCompletion* routine is called at IRQL = PASSIVE_LEVEL or IRQL = DISPATCH_LEVEL.

### Examples

To define a *PowerCompletion* callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a *PowerCompletion* callback routine that is named `MyPowerCompletion`, use the REQUEST_POWER_COMPLETE type as shown in this code example:

```cpp
REQUEST_POWER_COMPLETE MyPowerCompletion;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
VOID
  MyPowerCompletion(
    PDEVICE_OBJECT DeviceObject,
    UCHAR MinorFunction,
    POWER_STATE PowerState,
    PVOID Context,
    PIO_STATUS_BLOCK IoStatus
    )
  {
      // Function body
  }
```

The REQUEST_POWER_COMPLETE function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the REQUEST_POWER_COMPLETE function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

[**DEVICE_OBJECT**](./ns-wdm-_device_object.md)

[**IO_STATUS_BLOCK**](./ns-wdm-_io_status_block.md)

[IRP_MJ_POWER](/windows-hardware/drivers/kernel/irp-mj-power)

[IRP_MN_QUERY_POWER](/windows-hardware/drivers/kernel/irp-mn-query-power)

[IRP_MN_SET_POWER](/windows-hardware/drivers/kernel/irp-mn-set-power)

[IRP_MN_WAIT_WAKE](/windows-hardware/drivers/kernel/irp-mn-wait-wake)

[IoCompletion](./nc-wdm-io_completion_routine.md)

[PoRequestPowerIrp](./nf-wdm-porequestpowerirp.md)