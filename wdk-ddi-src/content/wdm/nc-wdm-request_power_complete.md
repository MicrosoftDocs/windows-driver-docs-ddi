---
UID: NC:wdm.REQUEST_POWER_COMPLETE
title: REQUEST_POWER_COMPLETE (wdm.h)
description: The PowerCompletion callback routine completes the processing of a power IRP.
old-location: kernel\powercompletion.htm
tech.root: kernel
ms.assetid: 2272790e-324a-4bd4-86ed-b76305a2940b
ms.date: 04/30/2018
keywords: ["REQUEST_POWER_COMPLETE callback function"]
ms.keywords: PowerCompletion, PowerCompletion routine [Kernel-Mode Driver Architecture], REQUEST_POWER_COMPLETE, kernel.powercompletion, wdm/PowerCompletion
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows 2000 and later versions of Windows.
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
 - PowerCompletion
---

# REQUEST_POWER_COMPLETE callback function


## -description

The <i>PowerCompletion</i> callback routine completes the processing of a power IRP.

## -parameters

### -param DeviceObject 

[in]
A pointer to the target <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> for the completed power IRP.

### -param MinorFunction 

[in]
Specifies the minor function code in the power IRP. For more information, see the list of supported <b>IRP_MN_<i>XXX</i></b> codes in the Remarks section.

### -param PowerState 

[in]
Specifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/device-power-states">device power state</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/system-power-states">system power state</a> that was passed to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-porequestpowerirp">PoRequestPowerIrp</a> routine.

### -param Context 

[in, optional]
A pointer to the context that was passed to <b>PoRequestPowerIrp</b>.

### -param IoStatus 

[in]
A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a> structure for the completed IRP.

## -remarks

A driver that sends a power IRP might need to perform additional tasks after all other drivers have completed the IRP. If so, the sending driver should register a <i>PowerCompletion</i> callback routine during the call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-porequestpowerirp">PoRequestPowerIrp</a> routine that allocates the IRP.

A driver's <i>PowerCompletion</i> callback routine is used only for <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-power">IRP_MJ_POWER</a> IRPs that have minor IRP codes of <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-set-power">IRP_MN_SET_POWER</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-power">IRP_MN_QUERY_POWER</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-wait-wake">IRP_MN_WAIT_WAKE</a>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/sending-irp-mn-query-power-or-irp-mn-set-power-for-device-power-states">Sending IRP_MN_QUERY_POWER or IRP_MN_SET_POWER for Device Power States</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/wait-wake-callback-routines">Wait/Wake Callback Routines</a>.

The I/O manager calls the sending driver's <i>PowerCompletion</i> routine only after the I/O manager has called all the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_completion_routine">IoCompletion</a> routines that were set by other drivers as they passed the IRP down the stack. The <i>PowerCompletion</i> routine performs any additional tasks that the sender of the IRP requires after all other drivers have completed the IRP. The <i>PowerCompletion</i> routine should not free the IRP—the power manager does that.

In Windows 2000 and later versions of Windows, the <i>PowerCompletion</i> routine is called at IRQL = PASSIVE_LEVEL or IRQL = DISPATCH_LEVEL. In Windows 98/Me, the <i>PowerCompletion</i> routine is always called at IRQL = PASSIVE_LEVEL, and drivers must complete IRPs at IRQL = PASSIVE_LEVEL.



#### Examples

To define a <i>PowerCompletion</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>PowerCompletion</i> callback routine that is named <code>MyPowerCompletion</code>, use the REQUEST_POWER_COMPLETE type as shown in this code example:


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

The REQUEST_POWER_COMPLETE function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the REQUEST_POWER_COMPLETE function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-power">IRP_MJ_POWER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-power">IRP_MN_QUERY_POWER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-set-power">IRP_MN_SET_POWER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-wait-wake">IRP_MN_WAIT_WAKE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_completion_routine">IoCompletion</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-porequestpowerirp">PoRequestPowerIrp</a>

