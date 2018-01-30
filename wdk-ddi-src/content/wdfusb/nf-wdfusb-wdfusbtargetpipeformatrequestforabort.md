---
UID: NF:wdfusb.WdfUsbTargetPipeFormatRequestForAbort
title: WdfUsbTargetPipeFormatRequestForAbort function
author: windows-driver-content
description: The WdfUsbTargetPipeFormatRequestForAbort method builds an abort request for a specified USB pipe, but it does not send the request.
old-location: wdf\wdfusbtargetpipeformatrequestforabort.htm
old-project: wdf
ms.assetid: 79cf94e4-c362-4ed4-882e-771cd4f6ed48
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfUsbTargetPipeFormatRequestForAbort method, kmdf.wdfusbtargetpipeformatrequestforabort, wdfusb/WdfUsbTargetPipeFormatRequestForAbort, wdf.wdfusbtargetpipeformatrequestforabort, PFN_WDFUSBTARGETPIPEFORMATREQUESTFORABORT, DFUsbRef_d99442d6-818c-4c46-8df2-dd5e2346aa5f.xml, WdfUsbTargetPipeFormatRequestForAbort
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfUsbTargetPipeFormatRequestForAbort
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfUsbTargetPipeFormatRequestForAbort function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetPipeFormatRequestForAbort</b> method builds an abort request for a specified USB pipe, but it does not send the request.


## -syntax


````
NTSTATUS WdfUsbTargetPipeFormatRequestForAbort(
  _In_ WDFUSBPIPE Pipe,
  _In_ WDFREQUEST Request
);
````


## -parameters




### -param Pipe [in]

A handle to a framework pipe object that was obtained by calling <a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetconfiguredpipe.md">WdfUsbInterfaceGetConfiguredPipe</a>. 


### -param Request [in]

A handle to a framework request object. For more information, see the following Remarks section.


## -returns


<b>WdfUsbTargetPipeFormatRequestForAbort</b> returns the I/O target's completion status value if the operation succeeds. Otherwise, this method can return one of the following values:
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
The I/O request packet (<a href="..\wdm\ns-wdm-_irp.md">IRP</a>) that the <i>Request</i> parameter represents does not provide enough <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a> structures to allow the driver to forward the request.

</td>
</tr>
</table> 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


Use <b>WdfUsbTargetPipeFormatRequestForAbort</b>, followed by <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>, to send a USB abort request either synchronously or asynchronously. Alternatively, use the <a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipeabortsynchronously.md">WdfUsbTargetPipeAbortSynchronously</a> method to send a request synchronously. 

A USB abort request causes the driver's I/O target to cancel all of the I/O requests that have been sent to a pipe. When a driver calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>, the framework sends a <a href="..\usb\ns-usb-_urb_header.md">URB_FUNCTION_ABORT_PIPE</a> request to the I/O target. For more information about canceling operations on a USB pipe (also called "aborting a pipe"), see the USB specification.

You can forward an I/O request that your driver received in an I/O queue, or you can create and send a new request. 

To forward an I/O request that your driver received in an I/O queue, specify the received request's handle for the <b>WdfUsbTargetPipeFormatRequestForAbort</b> method's <i>Request</i> parameter.

To create a new I/O request, call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a> to preallocate a request object. Supply the request handle for the <b>WdfUsbTargetPipeFormatRequestForAbort</b> method's <i>Request</i> parameter. You can reuse the request object by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>. Your driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function can preallocate request objects for a device.

After calling <b>WdfUsbTargetPipeFormatRequestForAbort</b> to format an I/O request, the driver must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a> to send the request (either synchronously or asynchronously) to an I/O target.

Multiple calls to <b>WdfUsbTargetPipeFormatRequestForAbort</b> that use the same request do not cause additional resource allocations. Therefore, to reduce the chance that <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a> will return STATUS_INSUFFICIENT_RESOURCES, your driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function can call <b>WdfRequestCreate</b> to preallocate one or more request objects for a device. The driver can subsequently reuse (call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>), reformat (call <b>WdfUsbTargetPipeFormatRequestForAbort</b>), and resend (call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>) each request object without risking a STATUS_INSUFFICIENT_RESOURCES return value from a later call to <b>WdfRequestCreate</b>. All subsequent calls to <b>WdfUsbTargetPipeFormatRequestForAbort</b> for the reused request object will return STATUS_SUCCESS, if parameter values do not change. (If the driver does not call the same request-formatting method each time, additional resources might be allocated.)

For information about obtaining status information after an I/O request completes, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">Obtaining Completion Information</a>.

For more information about the <b>WdfUsbTargetPipeFormatRequestForAbort</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.



## -see-also

<a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetconfiguredpipe.md">WdfUsbInterfaceGetConfiguredPipe</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetPipeFormatRequestForAbort method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

