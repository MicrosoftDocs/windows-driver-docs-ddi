---
UID: NC:sercx.EVT_SERCX2_SET_WAIT_MASK
title: EVT_SERCX2_SET_WAIT_MASK (sercx.h)
description: The EvtSerCx2SetWaitMask event callback function is called by version 2 of the serial framework extension (SerCx2) to configure the serial controller to monitor a set of hardware events that are specified by a wait mask.
old-location: serports\evtsercx2setwaitmask.htm
tech.root: serports
ms.assetid: C248FEF0-8E0B-4296-940E-763165F80617
ms.date: 04/23/2018
keywords: ["EVT_SERCX2_SET_WAIT_MASK callback function"]
ms.keywords: 2/EvtSerCx2SetWaitMask, EVT_SERCX2_SET_WAIT_MASK, EVT_SERCX2_SET_WAIT_MASK callback, EvtSerCx2SetWaitMask, EvtSerCx2SetWaitMask callback function [Serial Ports], serports.evtsercx2setwaitmask
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.irql: Called at IRQL <= DISPATCH_LEVEL.
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_SERCX2_SET_WAIT_MASK
 - sercx/EVT_SERCX2_SET_WAIT_MASK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - 2.0\Sercx.h
api_name:
 - EvtSerCx2SetWaitMask
---

# EVT_SERCX2_SET_WAIT_MASK callback function


## -description

The <i>EvtSerCx2SetWaitMask</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to configure the serial controller to monitor a set of hardware events that are specified by a wait mask.

## -parameters

### -param Device 

[in]
A WDFDEVICE handle to the framework device object that represents the serial controller. The serial controller driver created this object in its <a href="/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function. For more information, see <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a>.

### -param Request 

[in]
A WDFREQUEST handle to the framework request object that represents the <a href="/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_wait_mask">IOCTL_SERIAL_SET_WAIT_MASK</a> request.

### -param WaitMask 

[in]
The new wait mask. For more information, see Remarks.

## -remarks

Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the call to the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a> method that finishes the initialization of the framework device object for the serial controller.

When SerCx receives an <a href="/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_wait_mask">IOCTL_SERIAL_SET_WAIT_MASK</a> request from a client, the request handler in SerCx2 calls the <i>EvtSerCx2SetWaitMask</i> function, if it is implemented, to notify the driver that the wait mask has changed. If the wait mask is nonzero, the driver immediately starts to monitor the events in the new wait mask, and discards any old wait mask that might have been supplied in a previous <i>EvtSerCx2SetWaitMask</i> call. If the new wait mask is zero, the driver simply discards the old wait mask and ceases to monitor any wait mask events. For more information about the types of events that can be specified by a wait mask, see <a href="/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a>.

If the driver does not implement this function, SerCx2 fails all <a href="/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_wait_mask">IOCTL_SERIAL_SET_WAIT_MASK</a> requests with error status code STATUS_NOT_SUPPORTED.

To monitor the events in the wait mask, the <i>EvtSerCx2SetWaitMask</i> function typically enables interrupts for these events. Later, when an event in the wait mask is detected, the serial controller driver calls the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2completewait">SerCx2CompleteWait</a> method to notify SerCx2 of the event.

The <i>EvtSerCx2SetWaitMask</i> function is responsible for completing the <b>IOCTL_SERIAL_SET_WAIT_MASK</b> request pointed to by the <i>Request</i> parameter.  After the serial controller driver enables the necessary interrupts, it calls the <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a> method and supplies, as input parameters, the <i>Request</i> parameter value and a status value to indicate whether the request was successful.

Before the serial controller driver calls <b>WdfRequestComplete</b> to complete the request, the driver must finish any calls to <b>SerCx2CompleteWait</b> that might be still be pending due to events in the old wait mask.

Initially, after a client opens a logical connection to the serial port and before the first <i>EvtSerCx2SetWaitMask</i> call, the wait mask is effectively zero, and the serial controller driver is not monitoring any <a href="/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a> events.

SerCx2 fails an <b>IOCTL_SERIAL_SET_WAIT_MASK</b> request that has a wait mask that includes any of the following <a href="/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a> event flags:

<ul>
<li>SERIAL_EV_PERR</li>
<li>SERIAL_EV_RING</li>
<li>SERIAL_EV_RXFLAG</li>
</ul>
Thus, the wait mask supplied to your <i>EvtSerCx2SetWaitMask</i> function never contains any of the event flags in the preceding list.

If implemented, your <i>EvtSerCx2SetWaitMask</i> function should support the following event flags:

<ul>
<li>SERIAL_EV_CTS</li>
<li>SERIAL_EV_BREAK</li>
<li>SERIAL_EV_ERR</li>
</ul>
Also, if the serial controller has a <i>data set ready</i> (DSR) signal line, the <i>EvtSerCx2SetWaitMask</i> function should support SERIAL_EV_DSR. As an option, a driver can support any of the other event flags described in <a href="/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a>. If the wait mask specifies an event that the driver does not support, the <i>EvtSerCx2SetWaitMask</i> function should fail the request and set the status value in the request to STATUS_INVALID_PARAMETER.


#### Examples

To define an <i>EvtSerCx2SetWaitMask</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2SetWaitMask</i> callback function that is named <code>MySetWaitmask</code>, use the <b>EVT_SERCX2_SET_WAIT_MASK</b> function type, as shown in this code example:


```cpp
EVT_SERCX2_SET_WAIT_MASK  MySetWaitmask;
```

Then, implement your callback function as follows:


```cpp
_Use_decl_annotations_
VOID
  MySetWaitmask(
    WDFDEVICE  Device,
    WDFREQUEST Request,
    ULONG WaitMask
    )
  {...}
```

The <b>EVT_SERCX2_SET_WAIT_MASK</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_SET_WAIT_MASK</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_wait_mask">IOCTL_SERIAL_SET_WAIT_MASK</a>



<a href="/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2completewait">SerCx2CompleteWait</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a>