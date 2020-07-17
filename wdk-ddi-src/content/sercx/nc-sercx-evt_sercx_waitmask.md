---
UID: NC:sercx.EVT_SERCX_WAITMASK
title: EVT_SERCX_WAITMASK (sercx.h)
description: The EvtSerCxWaitmask event callback function configures the serial controller to monitor the events in a wait mask, which is a bitmask value that specifies a set of hardware events.
old-location: serports\evtsercxwaitmask.htm
tech.root: serports
ms.assetid: 41F60807-5A00-4B0E-A57D-70D25C73F575
ms.date: 04/23/2018
keywords: ["EVT_SERCX_WAITMASK callback function"]
ms.keywords: 1/EvtSerCxWaitmask, EVT_SERCX_WAITMASK, EVT_SERCX_WAITMASK callback, EvtSerCxWaitmask, EvtSerCxWaitmask callback function [Serial Ports], serports.evtsercxwaitmask
f1_keywords:
 - "sercx/EvtSerCxWaitmask"
 - "EvtSerCxWaitmask"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- 1.0\Sercx.h
api_name:
- EvtSerCxWaitmask
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SERCX_WAITMASK callback function


## -description


The <i>EvtSerCxWaitmask</i> event callback function configures the serial controller to monitor the events in a wait mask, which is a bitmask value that specifies a set of hardware events.


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.


## -returns



The <i>EvtSerCxWaitmask</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.




## -remarks



The serial controller driver implements this callback function. The serial framework extension (SerCx) calls this function to notify the driver when the wait mask changes. During this call, the <i>EvtSerCxWaitmask</i> function calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxgetwaitmask">SerCxGetWaitMask</a> method to get the new wait mask. The driver immediately starts to monitor the events in the new wait mask, and discards any old wait mask that might have been supplied in a previous <i>EvtSerCxWaitmask</i> call. If the new wait mask is zero, the driver simply discards the old wait mask and ceases to monitor any wait mask events.

When SerCx receives an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_wait_mask">IOCTL_SERIAL_SET_WAIT_MASK</a> request from a client, the request handler in SerCx calls the <i>EvtSerCxWaitmask</i> function to set the new wait mask. For more information about the types of events that can be specified by a wait mask, see <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a>.

The <i>EvtSerCxWaitmask</i> function configures the serial controller hardware to monitor the events in the new wait mask. Typically, the function enables interrupts for these events. After configuring the hardware, the function should return immediately, without waiting for an event in the wait mask to occur.

Later, when an event in the wait mask causes an interrupt to occur, the ISR in the serial controller driver schedules a DPC function to run. This DPC function calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxcompletewait">SerCxCompleteWait</a> method to notify SerCx of the event.

Initially, after a client opens a connection to the serial port and before the first <i>EvtSerCxWaitmask</i> call, the wait mask is effectively zero, and the serial controller driver is not monitoring any <b>SERIAL_EV_<i>XXX</i></b> events.

To register an <i>EvtSerCxWaitmask</i> callback function, the controller driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxinitialize">SerCxInitialize</a> method during the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback.


#### Examples

The function type for this callback is declared in Sercx.h, as follows.

<div class="code"><span codelanguage="cpp"><table>
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
To define an <i>EvtSerCxWaitmask</i> callback function that is named <code>MyEvtSerCxWaitmask</code>, you must first provide a function declaration that <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV) and other verification tools require, as follows.

<div class="code"><span codelanguage="cpp"><table>
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

<div class="code"><span codelanguage="cpp"><table>
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
For more information about SDV requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions Using Function Role Types for KMDF Drivers</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_wait_mask">IOCTL_SERIAL_SET_WAIT_MASK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_wait_on_mask">IOCTL_SERIAL_WAIT_ON_MASK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxgetwaitmask">SerCxGetWaitMask</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxinitialize">SerCxInitialize</a>
 

 

