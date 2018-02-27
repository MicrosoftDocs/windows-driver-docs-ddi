---
UID: NC:sercx.EVT_SERCX_WAITMASK
title: EVT_SERCX_WAITMASK
author: windows-driver-content
description: The EvtSerCxWaitmask event callback function configures the serial controller to monitor the events in a wait mask, which is a bitmask value that specifies a set of hardware events.
old-location: serports\evtsercxwaitmask.htm
old-project: serports
ms.assetid: 41F60807-5A00-4B0E-A57D-70D25C73F575
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 1/EvtSerCxWaitmask, EVT_SERCX_WAITMASK, EvtSerCxWaitmask, EvtSerCxWaitmask callback function [Serial Ports], serports.evtsercxwaitmask
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: Called at IRQL <= DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	1.0\Sercx.h
api_name:
-	EvtSerCxWaitmask
product: Windows
targetos: Windows
req.typenames: SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---

# EVT_SERCX_WAITMASK callback


## -description


The <i>EvtSerCxWaitmask</i> event callback function configures the serial controller to monitor the events in a wait mask, which is a bitmask value that specifies a set of hardware events.


## -prototype


````
EVT_SERCX_WAITMASK EvtSerCxWaitmask;

NTSTATUS EvtSerCxWaitmask(
  _In_ WDFDEVICE Device
)
{ ... }
````


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.


## -returns



The <i>EvtSerCxWaitmask</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.




## -remarks



The serial controller driver implements this callback function. The serial framework extension (SerCx) calls this function to notify the driver when the wait mask changes. During this call, the <i>EvtSerCxWaitmask</i> function calls the <a href="..\sercx\nf-sercx-sercxgetwaitmask.md">SerCxGetWaitMask</a> method to get the new wait mask. The driver immediately starts to monitor the events in the new wait mask, and discards any old wait mask that might have been supplied in a previous <i>EvtSerCxWaitmask</i> call. If the new wait mask is zero, the driver simply discards the old wait mask and ceases to monitor any wait mask events.

When SerCx receives an <a href="..\ntddser\ni-ntddser-ioctl_serial_set_wait_mask.md">IOCTL_SERIAL_SET_WAIT_MASK</a> request from a client, the request handler in SerCx calls the <i>EvtSerCxWaitmask</i> function to set the new wait mask. For more information about the types of events that can be specified by a wait mask, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a>.

The <i>EvtSerCxWaitmask</i> function configures the serial controller hardware to monitor the events in the new wait mask. Typically, the function enables interrupts for these events. After configuring the hardware, the function should return immediately, without waiting for an event in the wait mask to occur.

Later, when an event in the wait mask causes an interrupt to occur, the ISR in the serial controller driver schedules a DPC function to run. This DPC function calls the <a href="..\sercx\nf-sercx-sercxcompletewait.md">SerCxCompleteWait</a> method to notify SerCx of the event.

Initially, after a client opens a connection to the serial port and before the first <i>EvtSerCxWaitmask</i> call, the wait mask is effectively zero, and the serial controller driver is not monitoring any <b>SERIAL_EV_<i>XXX</i></b> events.

To register an <i>EvtSerCxWaitmask</i> callback function, the controller driver calls the <a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a> method during the <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback.


#### Examples

The function type for this callback is declared in Sercx.h, as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef NTSTATUS
  EVT_SERCX_WAITMASK(
    __in WDFDEVICE Device
    );</pre>
</td>
</tr>
</table></span></div>
To define an <i>EvtSerCxWaitmask</i> callback function that is named <code>MyEvtSerCxWaitmask</code>, you must first provide a function declaration that <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV) and other verification tools require, as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX_WAITMASK MyEvtSerCxWaitmask;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
  MyEvtSerCxWaitmask(
    __in WDFDEVICE Device
    )
{ ... }</pre>
</td>
</tr>
</table></span></div>
For more information about SDV requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions Using Function Role Types for KMDF Drivers</a>.

<div class="code"></div>



## -see-also

<a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a>



<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>



<a href="..\sercx\nf-sercx-sercxgetwaitmask.md">SerCxGetWaitMask</a>



<a href="..\ntddser\ni-ntddser-ioctl_serial_wait_on_mask.md">IOCTL_SERIAL_WAIT_ON_MASK</a>



<a href="..\ntddser\ni-ntddser-ioctl_serial_set_wait_mask.md">IOCTL_SERIAL_SET_WAIT_MASK</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX_WAITMASK callback function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

