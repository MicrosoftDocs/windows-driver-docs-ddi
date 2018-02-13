---
UID: NC:sercx.EVT_SERCX2_SET_WAIT_MASK
title: EVT_SERCX2_SET_WAIT_MASK
author: windows-driver-content
description: The EvtSerCx2SetWaitMask event callback function is called by version 2 of the serial framework extension (SerCx2) to configure the serial controller to monitor a set of hardware events that are specified by a wait mask.
old-location: serports\evtsercx2setwaitmask.htm
old-project: serports
ms.assetid: C248FEF0-8E0B-4296-940E-763165F80617
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercx2setwaitmask, EvtSerCx2SetWaitMask callback function [Serial Ports], EvtSerCx2SetWaitMask, EVT_SERCX2_SET_WAIT_MASK, EVT_SERCX2_SET_WAIT_MASK, 2/EvtSerCx2SetWaitMask
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	2.0\Sercx.h
apiname:
-	EvtSerCx2SetWaitMask
product: Windows
targetos: Windows
req.typenames: "*PSENSOR_VALUE_PAIR, SENSOR_VALUE_PAIR"
req.product: Windows 10 or later.
---

# EVT_SERCX2_SET_WAIT_MASK callback


## -description


The <i>EvtSerCx2SetWaitMask</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to configure the serial controller to monitor a set of hardware events that are specified by a wait mask.


## -prototype


````
EVT_SERCX2_SET_WAIT_MASK EvtSerCx2SetWaitMask;

VOID EvtSerCx2SetWaitMask(
  _In_ WDFDEVICE  Device,
  _In_ WDFREQUEST Request,
  _In_ ULONG      WaitMask
)
{ ... }
````


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller. The serial controller driver created this object in its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function. For more information, see <a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a>.


### -param Request [in]

A WDFREQUEST handle to the framework request object that represents the <a href="..\ntddser\ni-ntddser-ioctl_serial_set_wait_mask.md">IOCTL_SERIAL_SET_WAIT_MASK</a> request.


### -param WaitMask [in]

The new wait mask. For more information, see Remarks.


## -returns



None.




## -remarks



Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the call to the <a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a> method that finishes the initialization of the framework device object for the serial controller.

When SerCx receives an <a href="..\ntddser\ni-ntddser-ioctl_serial_set_wait_mask.md">IOCTL_SERIAL_SET_WAIT_MASK</a> request from a client, the request handler in SerCx2 calls the <i>EvtSerCx2SetWaitMask</i> function, if it is implemented, to notify the driver that the wait mask has changed. If the wait mask is nonzero, the driver immediately starts to monitor the events in the new wait mask, and discards any old wait mask that might have been supplied in a previous <i>EvtSerCx2SetWaitMask</i> call. If the new wait mask is zero, the driver simply discards the old wait mask and ceases to monitor any wait mask events. For more information about the types of events that can be specified by a wait mask, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a>.

If the driver does not implement this function, SerCx2 fails all <a href="..\ntddser\ni-ntddser-ioctl_serial_set_wait_mask.md">IOCTL_SERIAL_SET_WAIT_MASK</a> requests with error status code STATUS_NOT_SUPPORTED.

To monitor the events in the wait mask, the <i>EvtSerCx2SetWaitMask</i> function typically enables interrupts for these events. Later, when an event in the wait mask is detected, the serial controller driver calls the <a href="..\sercx\nf-sercx-sercx2completewait.md">SerCx2CompleteWait</a> method to notify SerCx2 of the event.

The <i>EvtSerCx2SetWaitMask</i> function is responsible for completing the <b>IOCTL_SERIAL_SET_WAIT_MASK</b> request pointed to by the <i>Request</i> parameter.  After the serial controller driver enables the necessary interrupts, it calls the <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a> method and supplies, as input parameters, the <i>Request</i> parameter value and a status value to indicate whether the request was successful.

Before the serial controller driver calls <b>WdfRequestComplete</b> to complete the request, the driver must finish any calls to <b>SerCx2CompleteWait</b> that might be still be pending due to events in the old wait mask.

Initially, after a client opens a logical connection to the serial port and before the first <i>EvtSerCx2SetWaitMask</i> call, the wait mask is effectively zero, and the serial controller driver is not monitoring any <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a> events.

SerCx2 fails an <b>IOCTL_SERIAL_SET_WAIT_MASK</b> request that has a wait mask that includes any of the following <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a> event flags:

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
Also, if the serial controller has a <i>data set ready</i> (DSR) signal line, the <i>EvtSerCx2SetWaitMask</i> function should support SERIAL_EV_DSR. As an option, a driver can support any of the other event flags described in <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a>. If the wait mask specifies an event that the driver does not support, the <i>EvtSerCx2SetWaitMask</i> function should fail the request and set the status value in the request to STATUS_INVALID_PARAMETER.


#### Examples

To define an <i>EvtSerCx2SetWaitMask</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2SetWaitMask</i> callback function that is named <code>MySetWaitmask</code>, use the <b>EVT_SERCX2_SET_WAIT_MASK</b> function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_SET_WAIT_MASK  MySetWaitmask;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
  MySetWaitmask(
    WDFDEVICE  Device,
    WDFREQUEST Request,
    ULONG WaitMask
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_SERCX2_SET_WAIT_MASK</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_SET_WAIT_MASK</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also

<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>



<a href="..\sercx\nf-sercx-sercx2completewait.md">SerCx2CompleteWait</a>



<a href="..\ntddser\ni-ntddser-ioctl_serial_set_wait_mask.md">IOCTL_SERIAL_SET_WAIT_MASK</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a>



<a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_SET_WAIT_MASK callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

