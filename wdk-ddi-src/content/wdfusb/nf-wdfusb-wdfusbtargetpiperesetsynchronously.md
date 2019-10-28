---
UID: NF:wdfusb.WdfUsbTargetPipeResetSynchronously
title: WdfUsbTargetPipeResetSynchronously function (wdfusb.h)
description: The WdfUsbTargetPipeResetSynchronously method builds a reset request and sends it synchronously to a specified USB pipe.
old-location: wdf\wdfusbtargetpiperesetsynchronously.htm
tech.root: wdf
ms.assetid: 7d29fb09-0ddc-4b61-8f85-c0e69d891bc5
ms.date: 02/26/2018
ms.keywords: DFUsbRef_07fcbce0-9754-49c9-988b-0875242739a0.xml, WdfUsbTargetPipeResetSynchronously, WdfUsbTargetPipeResetSynchronously method, kmdf.wdfusbtargetpiperesetsynchronously, wdf.wdfusbtargetpiperesetsynchronously, wdfusb/WdfUsbTargetPipeResetSynchronously
ms.topic: function
f1_keywords:
 - "wdfusb/WdfUsbTargetPipeResetSynchronously"
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, RequestForUrbXrb, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfUsbTargetPipeResetSynchronously
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetPipeResetSynchronously function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbTargetPipeResetSynchronously</b> method builds a reset request and sends it synchronously to a specified USB pipe.


## -parameters




### -param Pipe [in]

A handle to a framework pipe object that was obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfacegetconfiguredpipe">WdfUsbInterfaceGetConfiguredPipe</a>. 


### -param Request [in, optional]

A handle to a framework request object. This parameter is optional and can be <b>NULL</b>. For more information, see the following Remarks section.


### -param RequestOptions [in, optional]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure that specifies options for the request. This pointer is optional and can be <b>NULL</b>. For more information, see the following Remarks section.


## -returns



<b>WdfUsbTargetPipeResetSynchronously</b> returns the USB I/O target's completion status value if the operation succeeds. Otherwise, this method can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure that the <i>RequestOptions</i> parameter specified was incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Insufficient memory was available.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The caller's IRQL was not PASSIVE_LEVEL, or the I/O request that the <i>Request</i> parameter specified was already queued to an I/O target.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_IO_TIMEOUT</b></dt>
</dl>
</td>
<td width="60%">
The driver supplied a time-out value and the request did not complete within the allotted time. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_REQUEST_NOT_ACCEPTED</b></dt>
</dl>
</td>
<td width="60%">
The I/O request packet (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>) that the <i>Request</i> parameter represents does not provide enough <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a> structures to allow the driver to forward the request.

</td>
</tr>
</table>
 

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Use the <b>WdfUsbTargetPipeResetSynchronously</b> method to send a USB reset request synchronously. To send such requests asynchronously use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetpipeformatrequestforreset">WdfUsbTargetPipeFormatRequestForReset</a>, followed by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsend">WdfRequestSend</a>.

Before the framework resets the I/O target's USB pipe, it cancels all I/O requests that remain in the I/O target's queue. The driver must not send additional I/O requests to the I/O target until <b>WdfUsbTargetPipeResetSynchronously</b> returns.

The driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetstop">WdfIoTargetStop</a> before it calls <b>WdfUsbTargetPipeResetSynchronously</b>. After <b>WdfUsbTargetPipeResetSynchronously</b> returns, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetstart">WdfIoTargetStart</a>.

When a driver calls <b>WdfUsbTargetPipeResetSynchronously</b>, the framework sends a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_header">URB_FUNCTION_RESET_PIPE</a> request to the I/O target. For more information about resetting a USB pipe, see the USB specification.

The <b>WdfUsbTargetPipeResetSynchronously</b> method does not return until the request has completed, unless the driver supplies a time-out value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure that the <i>RequestOptions</i> parameter points to, or unless an error is detected.

You can forward an I/O request that your driver received in an I/O queue, or you can create and send a new request.

To forward an I/O request that your driver received in an I/O queue, specify the received request's handle for the <b>WdfUsbTargetPipeResetSynchronously</b> method's <i>Request</i> parameter.

To create and send a new request, either supply a <b>NULL</b> request handle for the <i>Request</i> parameter, or create a new request object and supply its handle:

<ul>
<li>
If you supply a <b>NULL</b> request handle, the framework uses an internal request object. This technique is simple to use, but the driver cannot cancel the request.

</li>
<li>
If you call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcreate">WdfRequestCreate</a> to create one or more request objects, you can reuse these request objects by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestreuse">WdfRequestReuse</a>. This technique enables your driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function to preallocate request objects for a device. Additionally, another driver thread can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcancelsentrequest">WdfRequestCancelSentRequest</a> to cancel the request, if necessary.

</li>
</ul>
Your driver can specify a non-<b>NULL</b> <i>RequestOptions</i> parameter, whether the driver provides a non-<b>NULL</b> or a <b>NULL</b> <i>Request</i> parameter. You can, for example, use the <i>RequestOptions</i> parameter to specify a time-out value. 

For information about obtaining status information after an I/O request completes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">Obtaining Completion Information</a>.

For more information about the <b>WdfUsbTargetPipeResetSynchronously</b> method and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example sends a reset request to a USB device's pipe.

```cpp
NTSTATUS  status;

status = WdfUsbTargetPipeResetSynchronously(
                                            Pipe, 
                                            WDF_NO_HANDLE,
                                            NULL
                                            );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfobjectdereference">WdfObjectDereference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcancelsentrequest">WdfRequestCancelSentRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsend">WdfRequestSend</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetpipeabortsynchronously">WdfUsbTargetPipeAbortSynchronously</a>
 

 

