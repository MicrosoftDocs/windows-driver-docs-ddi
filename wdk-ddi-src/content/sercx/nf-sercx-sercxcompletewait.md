---
UID: NF:sercx.SerCxCompleteWait
title: SerCxCompleteWait function
author: windows-driver-content
description: The SerCxCompleteWait method notifies the serial framework extension (SerCx) that an event in the current wait mask has occurred.
old-location: serports\sercxcompletewait.htm
old-project: serports
ms.assetid: 9318AB76-48ED-49FF-A4ED-17A07D43A0F8
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: 1/SerCxCompleteWait, SerCxCompleteWait method [Serial Ports], serports.sercxcompletewait, SerCxCompleteWait
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Universal
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	1.0\Sercx.h
apiname:
-	SerCxCompleteWait
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SerCxCompleteWait function


## -description


The <b>SerCxCompleteWait</b> method notifies the serial framework extension (SerCx) that an event in the current wait mask has occurred.


## -syntax


````
NTSTATUS SerCxCompleteWait(
  [in] WDFDEVICE Device,
  [in] ULONG     Event
);
````


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.


### -param Event [in]

The type of event that is ending the current wait operation.  This parameter is a wait mask value. Each event type corresponds to a particular bit in the wait mask. This bit is set to indicate that the corresponding event has occurred. For more information about the types of events that can be specified by a wait mask, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a>.


## -returns


<b>SerCxCompleteWait</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status code.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The specified event is not included in the current wait mask.

</td>
</tr>
</table> 



## -remarks


When SerCx receives an <a href="..\ntddser\ni-ntddser-ioctl_serial_set_wait_mask.md">IOCTL_SERIAL_SET_WAIT_MASK</a> request from a client, the request handler in SerCx calls the <a href="..\sercx\nc-sercx-evt_sercx_waitmask.md">EvtSerCxWaitmask</a> callback function to notify the serial controller driver that the wait mask has changed. The wait mask specifies a set of hardware events for the serial controller to monitor. During this call, the driver discards any old wait mask that might have been specified in a previous <i>EvtSerCxWaitmask</i> call, and then configures the serial controller hardware to detect the events in the new wait mask.

Later, when an event in the new wait mask occurs, the driver calls <b>SerCxCompleteWait</b> to notify SerCx of the event. If a previously sent <a href="..\ntddser\ni-ntddser-ioctl_serial_wait_on_mask.md">IOCTL_SERIAL_WAIT_ON_MASK</a> request is pending, <b>SerCxCompleteWait</b> completes this request with a status of STATUS_SUCCESS and an output wait mask that indicates which event occurred. Otherwise, <b>SerCxCompleteWait</b> stores the event in its internal event history in anticipation of a future <b>IOCTL_SERIAL_WAIT_ON_MASK</b> request.



## -see-also

<a href="..\ntddser\ni-ntddser-ioctl_serial_set_wait_mask.md">IOCTL_SERIAL_SET_WAIT_MASK</a>

<a href="..\sercx\nf-sercx-sercxgetwaitmask.md">SerCxGetWaitMask</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a>

<a href="..\sercx\nc-sercx-evt_sercx_waitmask.md">EvtSerCxWaitmask</a>

<a href="..\ntddser\ni-ntddser-ioctl_serial_wait_on_mask.md">IOCTL_SERIAL_WAIT_ON_MASK</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCxCompleteWait method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

