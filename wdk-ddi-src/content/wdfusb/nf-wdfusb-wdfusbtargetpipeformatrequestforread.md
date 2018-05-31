---
UID: NF:wdfusb.WdfUsbTargetPipeFormatRequestForRead
title: WdfUsbTargetPipeFormatRequestForRead function
author: windows-driver-content
description: The WdfUsbTargetPipeFormatRequestForRead method builds a read request for a USB input pipe, but it does not send the request.
old-location: wdf\wdfusbtargetpipeformatrequestforread.htm
old-project: wdf
ms.assetid: 33a6f597-2f33-4214-80c1-8bded182800a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_5cd8eeb4-5822-44ef-ba50-e978b780463b.xml, WdfUsbTargetPipeFormatRequestForRead, WdfUsbTargetPipeFormatRequestForRead method, kmdf.wdfusbtargetpipeformatrequestforread, wdf.wdfusbtargetpipeformatrequestforread, wdfusb/WdfUsbTargetPipeFormatRequestForRead
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, RequestFormattedValid, RequestSendAndForgetNoFormatting, RequestSendAndForgetNoFormatting2, UsbKmdfIrql, UsbKmdfIrql2
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
-	WdfUsbTargetPipeFormatRequestForRead
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetPipeFormatRequestForRead function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetPipeFormatRequestForRead</b> method builds a read request for a USB input pipe, but it does not send the request.


## -parameters




### -param Pipe [in]

A handle to a framework pipe object that was obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550057">WdfUsbInterfaceGetConfiguredPipe</a>. 


### -param Request [in]

A handle to a framework request object. For more information, see the following Remarks section.


### -param ReadMemory [in, optional]

A handle to a framework memory object. This object represents a buffer that will receive data from the pipe. The buffer size must be a multiple of the pipe's maximum packet size unless the driver has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff551160">WdfUsbTargetPipeSetNoMaximumPacketSizeCheck</a>. For more information about this buffer, see the following Remarks section.


### -param ReadOffset [in, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/Ff548718">WDFMEMORY_OFFSET</a> structure that supplies optional byte offset and length values. The framework uses these values to determine the beginning address and length, within the read buffer, for the data transfer. If this pointer is <b>NULL</b>, the data transfer begins at the beginning of the buffer, and the transfer size is the buffer size.


## -returns



<b>WdfUsbTargetPipeFormatRequestForRead</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return one of the following values:

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
An invalid memory descriptor was specified, the pipe's type was not valid, the transfer direction was invalid, or the specified I/O request was already queued to an I/O target.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INTEGER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The offset that the <i>Offset</i> parameter specified was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_BUFFER_SIZE</b></dt>
</dl>
</td>
<td width="60%">
The buffer size was not a multiple of the pipe's maximum packet size. The buffer size must be a multiple of the pipe's maximum packet size unless the driver has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff551160">WdfUsbTargetPipeSetNoMaximumPacketSizeCheck</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_REQUEST_NOT_ACCEPTED</b></dt>
</dl>
</td>
<td width="60%">
The I/O request packet (<a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>) that the <i>Request</i> parameter represents does not provide enough <a href="https://msdn.microsoft.com/library/windows/hardware/ff550659">IO_STACK_LOCATION</a> structures to allow the driver to forward the request.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Use <b>WdfUsbTargetPipeFormatRequestForRead</b>, followed by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>, to send read requests either synchronously or asynchronously. Alternatively, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551155">WdfUsbTargetPipeReadSynchronously</a> method to send read requests synchronously. 

The pipe that the <i>Pipe</i> parameter specifies must be an input pipe, and the pipe's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439450">type</a> must be <b>WdfUsbPipeTypeBulk</b> or <b>WdfUsbPipeTypeInterrupt</b>.

You can forward an I/O request that your driver received in an I/O queue, or you can create and send a new request. In either case, the framework requires a request object and some buffer space.

To forward an I/O request that your driver received in an I/O queue:

<ol>
<li>
Specify the received request's handle for the <b>WdfUsbTargetPipeFormatRequestForRead</b> method's <i>Request</i> parameter.

</li>
<li>
Use the received request's output buffer for the <b>WdfUsbTargetPipeFormatRequestForRead</b> method's <i>ReadMemory</i> parameter.

The driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550019">WdfRequestRetrieveOutputMemory</a> to obtain a handle to a framework memory object that represents the request's output buffer, and use that handle as the value for the <i>ReadMemory</i> parameter.

</li>
</ol>
For more information about forwarding an I/O request, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/forwarding-i-o-requests">Forwarding I/O Requests</a>.

Drivers often divide received I/O requests into smaller requests that they send to an I/O target, so your driver might create new requests.

To create a new I/O request:

<ol>
<li>
Create a new request object and supply its handle for the <b>WdfUsbTargetPipeFormatRequestForRead</b> method's <i>Request</i> parameter.

Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549951">WdfRequestCreate</a> to preallocate one or more request objects. You can reuse these request objects by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>. Your driver's <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function can preallocate request objects for a device.

</li>
<li>
Provide buffer space, and supply the buffer's handle for the <b>WdfUsbTargetPipeFormatRequestForRead</b> method's <i>ReadMemory</i> parameter. 

Your driver must specify this buffer space as a WDFMEMORY handle to framework-managed memory. Your driver can do either of the following:

<ul>
<li> Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548706">WdfMemoryCreate</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548712">WdfMemoryCreatePreallocated</a> to create a new memory buffer, if you want the driver to pass a new buffer to the I/O target.  </li>
<li> Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550019">WdfRequestRetrieveOutputMemory</a> to obtain a handle to the memory object that represents a received I/O request's buffer, if you want the driver to pass that buffer's contents to the I/O target. </li>
</ul>
Note that if your driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550019">WdfRequestRetrieveOutputMemory</a> and passes the memory handle to <b>WdfUsbTargetPipeFormatRequestForRead</b>, the driver must not complete the received I/O request until after the driver deletes, reuses, or reformats the new, driver-created request object. (<b>WdfUsbTargetPipeFormatRequestForRead</b> increments the memory object's reference count. Deleting, reusing, or reformatting a request object decrements the memory object's reference count.)

</li>
</ol>
After calling <b>WdfUsbTargetPipeFormatRequestForRead</b> to format an I/O request, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a> to send the request (either synchronously or asynchronously) to an I/O target.

Multiple calls to <b>WdfUsbTargetPipeFormatRequestForRead</b> that use the same request do not cause additional resource allocations. Therefore, to reduce the chance that <a href="https://msdn.microsoft.com/library/windows/hardware/ff549951">WdfRequestCreate</a> will return STATUS_INSUFFICIENT_RESOURCES, your driver's <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function can call <b>WdfRequestCreate</b> to preallocate one or more request objects for a device. The driver can subsequently reuse (call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>), reformat (call <b>WdfUsbTargetPipeFormatRequestForRead</b>), and resend (call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>) each request object without risking a STATUS_INSUFFICIENT_RESOURCES return value from a later call to <b>WdfRequestCreate</b>. All subsequent calls to <b>WdfUsbTargetPipeFormatRequestForRead</b> for the reused request object will return STATUS_SUCCESS, if parameter values do not change. (If the driver does not call the same request-formatting method each time, additional resources might be allocated.)

The framework sets the USBD_SHORT_TRANSFER_OK flag in its internal  <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a>. Setting this flag allows the last packet of a data transfer to be less than the maximum packet size.

For information about obtaining status information after an I/O request completes, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">Obtaining Completion Information</a>.

For more information about the <b>WdfUsbTargetPipeFormatRequestForRead</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example is from the <a href="http://go.microsoft.com/fwlink/p/?linkid=256131">kmdf_fx2</a> sample driver. This example is an <a href="https://msdn.microsoft.com/d6fbb153-1355-4e94-b5d3-a218bd8c565d">EvtIoRead</a> callback function that forwards a read request to a USB pipe. The example calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550019">WdfRequestRetrieveOutputMemory</a> to obtain the request's output buffer, and then it formats the read request so that the request can be sent to a USB pipe. Next, the example registers a <a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a> callback function. Finally, it sends the request to the USB pipe.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID 
OsrFxEvtIoRead(
    IN WDFQUEUE  Queue,
    IN WDFREQUEST  Request,
    IN size_t  Length
    )
{
    WDFUSBPIPE  pipe;
    NTSTATUS  status;
    WDFMEMORY  reqMemory;
    PDEVICE_CONTEXT  pDeviceContext;

    //
    // First, validate input parameters.
    //
    if (Length &gt; TEST_BOARD_TRANSFER_BUFFER_SIZE) {
        status = STATUS_INVALID_PARAMETER;
        goto Exit;
    }

    pDeviceContext = GetDeviceContext(WdfIoQueueGetDevice(Queue));
 
    pipe = pDeviceContext-&gt;BulkReadPipe;
 
    status = WdfRequestRetrieveOutputMemory(
                                            Request,
                                            &amp;reqMemory
                                            );
    if (!NT_SUCCESS(status)){
        goto Exit;
    }
 
    status = WdfUsbTargetPipeFormatRequestForRead(
                                                  pipe,
                                                  Request,
                                                  reqMemory,
                                                  NULL
                                                  ); 
    if (!NT_SUCCESS(status)) {
        goto Exit;
    }

    WdfRequestSetCompletionRoutine(
                                   Request,
                                   EvtRequestReadCompletionRoutine,
                                   pipe
                                   );
    if (WdfRequestSend(
                       Request,
                       WdfUsbTargetPipeGetIoTarget(pipe),
                       WDF_NO_SEND_OPTIONS
                       ) == FALSE) {
        status = WdfRequestGetStatus(Request);
        goto Exit;
    }

 
Exit:
    if (!NT_SUCCESS(status)) {
        WdfRequestCompleteWithInformation(
                                          Request,
                                          status,
                                          0
                                          );
    }
    return;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/Ff548718">WDFMEMORY_OFFSET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549948">WdfRequestCompleteWithInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549974">WdfRequestGetStatus</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550030">WdfRequestSetCompletionRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550057">WdfUsbInterfaceGetConfiguredPipe</a>
 

 

