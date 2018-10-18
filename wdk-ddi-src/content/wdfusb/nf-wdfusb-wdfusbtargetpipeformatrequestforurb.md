---
UID: NF:wdfusb.WdfUsbTargetPipeFormatRequestForUrb
title: WdfUsbTargetPipeFormatRequestForUrb function
author: windows-driver-content
description: The WdfUsbTargetPipeFormatRequestForUrb method builds an USB request for a specified USB pipe, using request parameters that a specified URB describes, but it does not send the request.
old-location: wdf\wdfusbtargetpipeformatrequestforurb.htm
tech.root: wdf
ms.assetid: 15df601c-6daf-4db1-8c80-678d6c43ac55
ms.date: 2/26/2018
ms.keywords: DFUsbRef_243c98bc-1bef-4da4-8f04-aa9055fb6351.xml, WdfUsbTargetPipeFormatRequestForUrb, WdfUsbTargetPipeFormatRequestForUrb method, kmdf.wdfusbtargetpipeformatrequestforurb, wdf.wdfusbtargetpipeformatrequestforurb, wdfusb/WdfUsbTargetPipeFormatRequestForUrb
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, RequestFormattedValid, RequestSendAndForgetNoFormatting, RequestSendAndForgetNoFormatting2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
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
api_name:
-	WdfUsbTargetPipeFormatRequestForUrb
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetPipeFormatRequestForUrb function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfUsbTargetPipeFormatRequestForUrb</b> method builds an USB request for a specified USB pipe, using request parameters that a specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> describes, but it does not send the request.


## -parameters




### -param PIPE

<p>A handle to a framework pipe object that was obtained by calling <a href="https://msdn.microsoft.com/library/Ff550057(v=VS.85).aspx"><b>WdfUsbInterfaceGetConfiguredPipe</b></a>. </p>


### -param Request [in]

A handle to a framework request object. For more information, see the following Remarks section.


### -param UrbMemory [in]

A handle to a framework memory object that contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> structure.

If the driver previously called <a href="https://msdn.microsoft.com/library/windows/hardware/hh439428">WdfUsbTargetDeviceCreateWithParameters</a> to create <i>UsbDevice</i>, the driver must use <a href="https://msdn.microsoft.com/library/windows/hardware/hh439423">WdfUsbTargetDeviceCreateUrb</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/hh439420">WdfUsbTargetDeviceCreateIsochUrb</a> to create the URB contained in this memory object. 


### -param UrbMemoryOffset [in, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/Ff548718">WDFMEMORY_OFFSET</a> structure that supplies optional byte offset and length values. The framework uses these values to determine the beginning address of the URB within the memory that <i>UrbMemory</i> specifies. If this pointer is <b>NULL</b>, the URB is located at the beginning of the <i>UrbMemory</i> memory. 


## -returns



<b>WdfUsbTargetPipeFormatRequestForUrb</b> returns the I/O target's completion status value if the operation succeeds. Otherwise, this method can return one of the following values:

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
<dt><b>STATUS_INTEGER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The offset that the <i>UsbMemoryOffset</i> parameter specified was invalid.

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



Use <b>WdfUsbTargetPipeFormatRequestForUrb</b>, followed by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>, to send a USB request either synchronously or asynchronously. Alternatively, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551158">WdfUsbTargetPipeSendUrbSynchronously</a> method to send a request synchronously. 

The framework does not examine the USB request. If the request changes the state of the USB pipe, the framework will not be aware of the change.

You can forward an I/O request that your driver received in an I/O queue, or you can create and send a new request. 

To forward an I/O request that your driver received in an I/O queue, specify the received request's handle for the <b>WdfUsbTargetPipeFormatRequestForUrb</b> method's <i>Request</i> parameter.

To create a new I/O request, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549951">WdfRequestCreate</a> to preallocate a request object. Supply the request handle for the <b>WdfUsbTargetPipeFormatRequestForUrb</b> method's <i>Request</i> parameter. You can reuse the request object by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>, so your driver's <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function can preallocate request objects for a device.

After calling <b>WdfUsbTargetPipeFormatRequestForUrb</b> to format an I/O request, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a> to send the request (either synchronously or asynchronously) to an I/O target.

Multiple calls to <b>WdfUsbTargetPipeFormatRequestForUrb</b> that use the same request do not cause additional resource allocations. Therefore, to reduce the chance that <a href="https://msdn.microsoft.com/library/windows/hardware/ff549951">WdfRequestCreate</a> will return STATUS_INSUFFICIENT_RESOURCES, your driver's <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function can call <b>WdfRequestCreate</b> to preallocate one or more request objects for a device. The driver can subsequently reuse (call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>), reformat (call <b>WdfUsbTargetPipeFormatRequestForUrb</b>), and resend (call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>) each request object without risking a STATUS_INSUFFICIENT_RESOURCES return value from a later call to <b>WdfRequestCreate</b>. All subsequent calls to <b>WdfUsbTargetPipeFormatRequestForUrb</b> for the reused request object will return STATUS_SUCCESS, if parameter values do not change. (If the driver does not call the same request-formatting method each time, additional resources might be allocated.)

For information about obtaining status information after an I/O request completes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">Obtaining Completion Information</a>.

For more information about the <b>WdfUsbTargetPipeFormatRequestForUrb</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example creates a memory object that represents a URB. Then, the example initializes the URB, formats a USB request that contains the URB, registers a <a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a> callback function, and sends the request.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>URB  urb;
PURB  pUrb = NULL;
WDFMEMORY  urbMemory
NTSTATUS status;

status = WdfMemoryCreate(
                         WDF_NO_OBJECT_ATTRIBUTES,
                         NonPagedPool,
                         0,
                         sizeof(struct _URB_GET_CURRENT_FRAME_NUMBER),
                         &amp;urbMemory,
                         NULL
                         );
if (!NT_SUCCESS(status)){
    return status;
}

pUrb = WdfMemoryGetBuffer(
                          urbMemory,
                          NULL
                          );

pUrb-&gt;UrbHeader.Length = (USHORT) sizeof(struct _URB_GET_CURRENT_FRAME_NUMBER);
pUrb-&gt;UrbHeader.Function = URB_FUNCTION_GET_CURRENT_FRAME_NUMBER;
pUrb-&gt;UrbGetCurrentFrameNumber.FrameNumber = 0; 

status = WdfUsbTargetPipeFormatRequestForUrb(
                                             pipe,
                                             Request,
                                             urbMemory,
                                             NULL
                                             );
if (!NT_SUCCESS(status)) {
    goto Exit;
}
WdfRequestSetCompletionRoutine(
                               Request,
                               UrbCompletionRoutine,
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
return;</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/Ff548718">WDFMEMORY_OFFSET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548706">WdfMemoryCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548715">WdfMemoryGetBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549948">WdfRequestCompleteWithInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550030">WdfRequestSetCompletionRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550057">WdfUsbInterfaceGetConfiguredPipe</a>
 

 

