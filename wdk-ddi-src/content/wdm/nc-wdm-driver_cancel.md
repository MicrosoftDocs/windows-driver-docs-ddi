---
UID: NC:wdm.DRIVER_CANCEL
title: DRIVER_CANCEL (wdm.h)
description: The Cancel routine cancels an I/O operation.
old-location: kernel\cancel.htm
tech.root: kernel
ms.assetid: 3e8053b7-a063-4143-a02d-35d917ca1e81
ms.date: 04/30/2018
keywords: ["DRIVER_CANCEL callback function"]
ms.keywords: Cancel, Cancel routine [Kernel-Mode Driver Architecture], DRIVER_CANCEL, DrvrRtns_790a0e91-0752-42ac-a5f0-4fee193765f0.xml, kernel.cancel, wdm/Cancel
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
req.irql: Called at DISPATCH_LEVEL (see Remarks section).
targetos: Windows
req.typenames: 
f1_keywords:
 - DRIVER_CANCEL
 - wdm/DRIVER_CANCEL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - Cancel
---

# DRIVER_CANCEL callback function


## -description

The <i>Cancel</i> routine cancels an I/O operation.

## -parameters

### -param DeviceObject 

[in, out]
Caller-supplied pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure. This is the device object for the target device, previously created by the driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> routine.

### -param Irp 

[in, out]
Caller-supplied pointer to an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> structure that describes the I/O operation to be canceled.

## -remarks

When a driver or other system component calls <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocancelirp">IoCancelIrp</a>, the I/O manager calls the IRP's <i>Cancel</i> routine, if one has been registered for the IRP.

To register a <i>Cancel</i> routine for an IRP, a driver can use either of the following two methods:

<ol>
<li>
A driver that provides a <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_startio">StartIo</a> routine and uses the I/O manager-supplied device queue can specify a <i>Cancel</i> routine when calling <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iostartpacket">IoStartPacket</a>.

</li>
<li>
A driver that creates and manages supplemental device queues can register a <i>Cancel</i> routine by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetcancelroutine">IoSetCancelRoutine</a>.

</li>
</ol>
Only one <i>Cancel</i> routine can be registered for an IRP at one time. 

The I/O manager calls <a href="/previous-versions/windows/hardware/drivers/ff548196(v=vs.85)">IoAcquireCancelSpinLock</a> before calling a driver's <i>Cancel</i> routine, so the <i>Cancel</i> routine must call <a href="/previous-versions/windows/hardware/drivers/ff549550(v=vs.85)">IoReleaseCancelSpinLock</a> at some point. The routine should not hold the spin lock longer than necessary.

The <i>Cancel</i> routine executes in an arbitrary thread context at IRQL = DISPATCH_LEVEL until it calls <b>IoReleaseCancelSpinLock</b>, which changes the IRQL to a caller-supplied value. The driver should specify <b>Irp->CancelIrql</b> for this value.

The <i>Cancel</i> routine must set the I/O status block's <b>Status</b> member to STATUS_CANCELLED, and set its <b>Information</b> member to zero. The routine must then complete the specified IRP by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocompleterequest">IoCompleteRequest</a>.

For detailed information about implementing a driver's <i>Cancel</i> routine, see <a href="/windows-hardware/drivers/kernel/canceling-irps">Canceling IRPs</a>.


#### Examples

To define a <i>Cancel</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>Cancel</i> callback routine that is named <code>MyCancel</code>, use the DRIVER_CANCEL type as shown in this code example:


```
DRIVER_CANCEL MyCancel;
```

Then, implement your callback routine as follows:


```
_Use_decl_annotations_
VOID
  MyCancel(
    struct _DEVICE_OBJECT  *DeviceObject,
    struct _IRP  *Irp
    )
  {
      // Function body
  }
```

The DRIVER_CANCEL function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the DRIVER_CANCEL function type in the header file are used. For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

<div class="code"></div>