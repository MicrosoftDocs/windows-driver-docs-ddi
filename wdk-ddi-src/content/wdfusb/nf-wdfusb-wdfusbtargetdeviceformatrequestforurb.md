---
UID: NF:wdfusb.WdfUsbTargetDeviceFormatRequestForUrb
title: WdfUsbTargetDeviceFormatRequestForUrb function
author: windows-driver-content
description: The WdfUsbTargetDeviceFormatRequestForUrb method builds an USB request for a specified USB device, using request parameters that are described by a URB, but it does not send the request.
old-location: wdf\wdfusbtargetdeviceformatrequestforurb.htm
old-project: wdf
ms.assetid: 886120f0-da2a-4a00-b440-ce1274c516d4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_c7b76463-570c-4f0d-b4d5-37ef192ba30f.xml, WdfUsbTargetDeviceFormatRequestForUrb, WdfUsbTargetDeviceFormatRequestForUrb method, kmdf.wdfusbtargetdeviceformatrequestforurb, wdf.wdfusbtargetdeviceformatrequestforurb, wdfusb/WdfUsbTargetDeviceFormatRequestForUrb
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	WdfUsbTargetDeviceFormatRequestForUrb
product: Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetDeviceFormatRequestForUrb function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfUsbTargetDeviceFormatRequestForUrb</b> method builds an USB request for a specified USB device, using request parameters that are described by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a>, but it does not send the request.


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/hh439428">WdfUsbTargetDeviceCreateWithParameters</a>.


### -param Request [in]

A handle to a framework request object. For more information, see the following Remarks section.


### -param UrbMemory [in]

A handle to a framework memory object that contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> structure or one of the structure's union members. (All of the URB structure's union members contain the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540409">_URB_HEADER</a> structure.) 

If the driver previously called <a href="https://msdn.microsoft.com/library/windows/hardware/hh439428">WdfUsbTargetDeviceCreateWithParameters</a> to create <i>UsbDevice</i>, the driver must use <a href="https://msdn.microsoft.com/library/windows/hardware/hh439423">WdfUsbTargetDeviceCreateUrb</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/hh439420">WdfUsbTargetDeviceCreateIsochUrb</a> to create the URB contained in this memory object. Otherwise, a bug check occurs.


### -param UrbMemoryOffset [in, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff561398">WDFMEMORY_OFFSET</a> structure that supplies optional byte offset and length values. The framework uses these values to determine the beginning address of the URB within the memory that <i>UrbMemory</i> specifies. If this pointer is <b>NULL</b>, the URB is located at the beginning of the <i>UrbMemory</i> memory. 


## -returns



<b>WdfUsbTargetDeviceFormatRequestForUrb</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return one of the following values:

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
There was insufficient memory.

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
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Use <b>WdfUsbTargetDeviceFormatRequestForUrb</b>, followed by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>, to send a USB control transfer request either synchronously or asynchronously. Alternatively, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550105">WdfUsbTargetDeviceSendUrbSynchronously</a> method to send a request synchronously. 

You can forward an I/O request that your driver received in an I/O queue, or you can create and send a new request. 

To forward an I/O request that your driver received in an I/O queue, specify the received request's handle for the <b>WdfUsbTargetDeviceFormatRequestForUrb</b> method's <i>Request</i> parameter.

To create a new I/O request, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549951">WdfRequestCreate</a> to preallocate a request object. Supply the request handle for the <b>WdfUsbTargetDeviceFormatRequestForUrb</b> method's <i>Request</i> parameter. You can reuse the request object by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>. Your driver's <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function can preallocate request objects for a device.

After calling <b>WdfUsbTargetDeviceFormatRequestForUrb</b> to format an I/O request, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a> to send the request (either synchronously or asynchronously) to an I/O target. Do not use the <a href="https://msdn.microsoft.com/6161bfd3-482c-4571-bd88-2e25d32b34a0">send and forget option</a> to send the request.

Multiple calls to <b>WdfUsbTargetDeviceFormatRequestForUrb</b> that use the same request do not cause additional resource allocations. Therefore, to reduce the chance that <a href="https://msdn.microsoft.com/library/windows/hardware/ff549951">WdfRequestCreate</a> will return STATUS_INSUFFICIENT_RESOURCES, your driver's <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function can call <b>WdfRequestCreate</b> to preallocate one or more request objects for a device. The driver can subsequently reuse (call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>), reformat (call <b>WdfUsbTargetDeviceFormatRequestForUrb</b>), and resend (call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>) each request object without risking a STATUS_INSUFFICIENT_RESOURCES return value from a later call to <b>WdfRequestCreate</b>. All subsequent calls to <b>WdfUsbTargetDeviceFormatRequestForUrb</b> for the reused request object will return STATUS_SUCCESS, if parameter values do not change. (If the driver does not call the same request-formatting method each time, additional resources might be allocated.)

For information about obtaining status information after an I/O request completes, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">Obtaining Completion Information</a>.

For more information about the <b>WdfUsbTargetDeviceFormatRequestForUrb</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example creates a memory object to hold a URB structure, initializes the URB structure, and calls <b>WdfUsbTargetDeviceFormatRequestForUrb</b> to format a request that uses the URB structure's contents. Then, the example registers a <a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a> callback function and sends the request to an I/O target.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDFMEMORY urbMemory;
URB *urbBuffer;

status = WdfMemoryCreate(
                         WDF_NO_OBJECT_ATTRIBUTES,
                         NonPagedPool,
                         0,
                         sizeof(struct _URB_CONTROL_GET_CONFIGURATION_REQUEST),
                         &amp;urbMemory,
                         NULL
                         );

if (!NT_SUCCESS(status)){
    return status;
}
urbBuffer = (PURB) WdfMemoryGetBuffer(
                                      urbMemory,
                                      NULL
                                      );
urbBuffer-&gt;UrbHeader.Function =  URB_FUNCTION_GET_CONFIGURATION;
urbBuffer-&gt;UrbHeader.Length = sizeof(struct _URB_CONTROL_GET_CONFIGURATION_REQUEST);
urbBuffer-&gt;UrbControlGetConfigurationRequest.TransferBufferLength = 1 ;
urbBuffer-&gt;UrbControlGetConfigurationRequest.TransferBufferMDL = NULL;
urbBuffer-&gt;UrbControlGetConfigurationRequest.TransferBuffer = outBuffer;
urbBuffer-&gt;UrbControlGetConfigurationRequest.UrbLink = NULL;

status = WdfUsbTargetDeviceFormatRequestForUrb(
                                               deviceContext-&gt;WdfUsbTargetDevice,
                                               request,
                                               urbMemory,
                                               NULL
                                               );
WdfRequestSetCompletionRoutine(
                              request,
                              MyCompletionRoutine,
                              NULL);

if (WdfRequestSend(
                   request,
                   WdfUsbTargetDeviceGetIoTarget(UsbDevice),
                   NULL
                   ) == FALSE) {
    status = WdfRequestGetStatus(request);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561398">WDFMEMORY_OFFSET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439428">WdfUsbTargetDeviceCreateWithParameters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550105">WdfUsbTargetDeviceSendUrbSynchronously</a>
 

 

