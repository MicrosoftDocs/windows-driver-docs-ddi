---
UID: NF:wdfusb.WdfUsbTargetPipeFormatRequestForReset
title: WdfUsbTargetPipeFormatRequestForReset function
author: windows-driver-content
description: The WdfUsbTargetPipeFormatRequestForReset method builds a reset request for a specified USB pipe, but it does not send the request.
old-location: wdf\wdfusbtargetpipeformatrequestforreset.htm
old-project: wdf
ms.assetid: 10f5296c-6be2-4f88-952b-b23e518b844a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_5a1aa46c-9d8a-4e6b-9003-723a65c314f3.xml, WdfUsbTargetPipeFormatRequestForReset, WdfUsbTargetPipeFormatRequestForReset method, kmdf.wdfusbtargetpipeformatrequestforreset, wdf.wdfusbtargetpipeformatrequestforreset, wdfusb/WdfUsbTargetPipeFormatRequestForReset
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
-	WdfUsbTargetPipeFormatRequestForReset
product: Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetPipeFormatRequestForReset function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetPipeFormatRequestForReset</b> method builds a reset request for a specified USB pipe, but it does not send the request.


## -parameters




### -param Pipe [in]

A handle to a framework pipe object that was obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550057">WdfUsbInterfaceGetConfiguredPipe</a>. 


### -param Request [in]

A handle to a framework request object. For more information, see the following Remarks section.


## -returns



<b>WdfUsbTargetPipeFormatRequestForReset</b> returns the USB I/O target's completion status value if the operation succeeds. Otherwise, this method can return one of the following values:

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



Use <b>WdfUsbTargetPipeFormatRequestForReset</b>, followed by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>, to send a USB reset request either synchronously or asynchronously. Alternatively, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551156">WdfUsbTargetPipeResetSynchronously</a> method to send a request synchronously. 

Before the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>, it must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548680">WdfIoTargetStop</a> and it must <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">complete</a> or <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/canceling-i-o-requests">cancel</a> all I/O requests that it has sent to the I/O target. The driver must not send additional I/O requests to the I/O target until the reset request completes.

When a driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>, the framework sends a <a href="https://msdn.microsoft.com/d23b9332-1e9d-4592-9674-3e5d8fc1d11e">URB_FUNCTION_RESET_PIPE</a> request to the I/O target. For more information about resetting a USB pipe, see the USB specification.

You can forward an I/O request that your driver received in an I/O queue, or you can create and send a new request. 

To forward an I/O request that your driver received in an I/O queue, specify the received request's handle for the <b>WdfUsbTargetPipeFormatRequestForReset</b> method's <i>Request</i> parameter.

To create a new I/O request, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549951">WdfRequestCreate</a> to preallocate a request object. Supply the request handle for the <b>WdfUsbTargetPipeFormatRequestForReset</b> method's <i>Request</i> parameter. You can reuse the request object by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>. Your driver's <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function can preallocate request objects for a device.

After calling <b>WdfUsbTargetPipeFormatRequestForReset</b> to format an I/O request, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a> to send the request (either synchronously or asynchronously) to an I/O target.

Multiple calls to <b>WdfUsbTargetPipeFormatRequestForReset</b> that use the same request do not cause additional resource allocations. Therefore, to reduce the chance that <a href="https://msdn.microsoft.com/library/windows/hardware/ff549951">WdfRequestCreate</a> will return STATUS_INSUFFICIENT_RESOURCES, your driver's <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function can call <b>WdfRequestCreate</b> to preallocate one or more request objects for a device. The driver can subsequently reuse (call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>), reformat (call <b>WdfUsbTargetPipeFormatRequestForReset</b>), and resend (call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>) each request object without risking a STATUS_INSUFFICIENT_RESOURCES return value from a later call to <b>WdfRequestCreate</b>. All subsequent calls to <b>WdfUsbTargetPipeFormatRequestForReset</b> for the reused request object will return STATUS_SUCCESS, if parameter values do not change. (If the driver does not call the same request-formatting method each time, additional resources might be allocated.)

For information about obtaining status information after an I/O request completes, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">Obtaining Completion Information</a>.

For more information about the <b>WdfUsbTargetPipeFormatRequestForReset</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example formats a reset request for a USB pipe, registers a <a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a> callback function, and sends the request.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>status = WdfUsbTargetPipeFormatRequestForReset(
                                               pipe,
                                               Request
                                               );
if (!NT_SUCCESS(status)) {
    goto Exit;
}

WdfRequestSetCompletionRoutine(
                               Request,
                               AbortCompletionRoutine,
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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550057">WdfUsbInterfaceGetConfiguredPipe</a>
 

 

