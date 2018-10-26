---
UID: NF:wdfusb.WdfUsbTargetDeviceFormatRequestForControlTransfer
title: WdfUsbTargetDeviceFormatRequestForControlTransfer function
author: windows-driver-content
description: The WdfUsbTargetDeviceFormatRequestForControlTransfer method builds a USB control transfer request, but it does not send the request.
old-location: wdf\wdfusbtargetdeviceformatrequestforcontroltransfer.htm
tech.root: wdf
ms.assetid: 72ba7550-9153-4ff7-8478-c9cc71151a25
ms.date: 02/26/2018
ms.keywords: DFUsbRef_7f2ef529-05f2-46c2-861e-d9557c6bb7bc.xml, WdfUsbTargetDeviceFormatRequestForControlTransfer, WdfUsbTargetDeviceFormatRequestForControlTransfer method, kmdf.wdfusbtargetdeviceformatrequestforcontroltransfer, wdf.wdfusbtargetdeviceformatrequestforcontroltransfer, wdfusb/WdfUsbTargetDeviceFormatRequestForControlTransfer
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, RequestFormattedValid, RequestForUrbXrb, RequestSendAndForgetNoFormatting, RequestSendAndForgetNoFormatting2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfUsbTargetDeviceFormatRequestForControlTransfer
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetDeviceFormatRequestForControlTransfer function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbTargetDeviceFormatRequestForControlTransfer</b> method builds a USB control transfer request, but it does not send the request.


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/hh439428">WdfUsbTargetDeviceCreateWithParameters</a>.


### -param Request [in]

A handle to a framework request object. For more information, see the following Remarks section.


### -param SetupPacket [in]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a> structure that describes the control transfer.


### -param TransferMemory [in, optional]

A handle to a framework memory object that describes either an input or an output buffer, depending on the device-specific command. This pointer is optional and can be <b>NULL</b>. For more information, see the following Remarks section.


### -param TransferOffset [in, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/Ff548718">WDFMEMORY_OFFSET</a> structure that supplies optional byte offset and length values. The framework uses these values to determine the beginning address and length, within the buffer that <i>TransferMemory</i> specifies. If this pointer is <b>NULL</b>, the framework uses the entire buffer. 


## -returns



<b>WdfUsbTargetDeviceFormatRequestForControlTransfer</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return one of the following values:

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
An invalid memory descriptor was specified, or the specified I/O request was already queued to an I/O target.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Use <b>WdfUsbTargetDeviceFormatRequestForControlTransfer</b>, followed by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>, to send a USB control transfer request either synchronously or asynchronously. Alternatively, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550104">WdfUsbTargetDeviceSendControlTransferSynchronously</a> method to send a request synchronously. 

You can forward an I/O request that your driver received in an I/O queue, or you can create and send a new request. In either case, the framework requires a request object and, depending on the type of control transfer, possibly some buffer space.

To forward an I/O request that your driver received in an I/O queue:

<ol>
<li>
Specify the received request's handle for the <b>WdfUsbTargetDeviceFormatRequestForControlTransfer</b> method's <i>Request</i> parameter.

</li>
<li>
Use the received request's input or output buffer for the <i>TransferMemory</i> parameter. 

The driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550015">WdfRequestRetrieveInputMemory</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550019">WdfRequestRetrieveOutputMemory</a> to obtain a handle to a framework memory object that represents the request's input or output buffer, and use that handle as the value for <i>TransferMemory</i>.

</li>
</ol>
To create a new I/O request and a new buffer:

<ol>
<li>
Create a new request object and supply its handle for the <b>WdfUsbTargetDeviceFormatRequestForControlTransfer</b> method's <i>Request</i> parameter.

Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549951">WdfRequestCreate</a> to preallocate one or more request objects. You can reuse these request objects by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>. Your driver's <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function can preallocate request objects for a device.

</li>
<li>
Provide buffer space, and supply the buffer's handle for the <b>WdfUsbTargetDeviceFormatRequestForControlTransfer</b> method's <i>TransferMemory</i> parameter.

Your driver must specify this buffer space as a WDFMEMORY handle to framework-managed memory. Your driver can do either of the following:

<ul>
<li> Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548706">WdfMemoryCreate</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548712">WdfMemoryCreatePreallocated</a> to create a new memory buffer, if you want the driver to pass a new buffer to the I/O target.  </li>
<li> Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550015">WdfRequestRetrieveInputMemory</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550019">WdfRequestRetrieveOutputMemory</a> to obtain a handle to the memory object that represents a received I/O request's buffer, if you want the driver to pass that buffer's contents to the I/O target. </li>
</ul>
Note that if your driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550015">WdfRequestRetrieveInputMemory</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550019">WdfRequestRetrieveOutputMemory</a> and passes the memory handle to <b>WdfUsbTargetDeviceFormatRequestForControlTransfer</b>, the driver must not complete the received I/O request until after the driver deletes, reuses, or reformats the new, driver-created request object. (<b>WdfUsbTargetDeviceFormatRequestForControlTransfer</b> increments the memory object's reference count. Deleting, reusing, or reformatting a request object decrements the memory object's reference count.)

</li>
</ol>
After calling <b>WdfUsbTargetDeviceFormatRequestForControlTransfer</b> to format an I/O request, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a> to send the request (either synchronously or asynchronously) to an I/O target.

Multiple calls to <b>WdfUsbTargetDeviceFormatRequestForControlTransfer</b> that use the same request do not cause additional resource allocations. Therefore, to reduce the chance that <a href="https://msdn.microsoft.com/library/windows/hardware/ff549951">WdfRequestCreate</a> will return STATUS_INSUFFICIENT_RESOURCES, your driver's <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549951">WdfRequestCreate</a> to preallocate one or more request objects for a device. The driver can subsequently reuse (call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>), reformat (call <b>WdfUsbTargetDeviceFormatRequestForControlTransfer</b>), and resend (call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>) each request object without risking a STATUS_INSUFFICIENT_RESOURCES return value from a later call to <b>WdfRequestCreate</b>. All subsequent calls to <b>WdfUsbTargetDeviceFormatRequestForControlTransfer</b> for the reused request object will return STATUS_SUCCESS, if parameter values do not change. (If the driver does not call the same request-formatting method each time, additional resources might be allocated.)

The framework sets the USBD_SHORT_TRANSFER_OK flag in its internal  <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a>. Setting this flag allows the last packet of a data transfer to be less than the maximum packet size.

For information about obtaining status information after an I/O request completes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">Obtaining Completion Information</a>.

For more information about the <b>WdfUsbTargetDeviceFormatRequestForControlTransfer</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example creates a request object and a memory object, and then it initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a> structure for a "get status" control transfer. Next, the example calls <b>WdfUsbTargetDeviceFormatRequestForControlTransfer</b> to format the request. Then, the example sets a <a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a> callback function and sends the request to an I/O target.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_USB_CONTROL_SETUP_PACKET packet;
NTSTATUS status;
WDF_OBJECT_ATTRIBUTES attributes;
WDFMEMORY memHandle;

WDF_OBJECT_ATTRIBUTES_INIT(&amp;attributes);

status = WdfRequestCreate(
                          &amp;attributes,
                          WdfUsbTargetDeviceGetIoTarget(
                              UsbTargetDevice,
                              &amp;request
                              )
                          );
if (!NT_SUCCESS(status)){
    return status;
}

WDF_OBJECT_ATTRIBUTES_INIT(&amp;attributes);
attributes.ParentObject = request;
status = WdfMemoryCreate(
                         &amp;attributes,
                         NonPagedPool,
                         0,
                         sizeof(USHORT),
                         &amp;memHandle,
                         NULL
                         );
if (!NT_SUCCESS(status)){
    return status;
}

WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS(
                                             &amp;packet,
                                             BmRequestToDevice,
                                             0
                                             );
status = WdfUsbTargetDeviceFormatRequestForControlTransfer(
                         UsbTargetDevice,
                         request,
                         &amp;packet,
                         memHandle,
                         NULL
                         );
if (!NT_SUCCESS(status)){
    return status;
}
WdfRequestSetCompletionRoutine(
                               request,
                               MyCompletionRoutine,
                               NULL
                               );
if (WdfRequestSend(
                   request,
                   WdfUsbTargetDeviceGetIoTarget(UsbTargetDevice),
                   NULL
                   ) == FALSE) {
    status = WdfRequestGetStatus(request);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552582">WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550104">WdfUsbTargetDeviceSendControlTransferSynchronously</a>
 

 

