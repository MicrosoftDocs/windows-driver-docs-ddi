---
UID: NF:wdfusb.WdfUsbTargetDeviceFormatRequestForCyclePort
title: WdfUsbTargetDeviceFormatRequestForCyclePort function
author: windows-driver-content
description: The WdfUsbTargetDeviceFormatRequestForCyclePort method builds a power-cycle request for the port to which a specified device is attached, but it does not send the request.
old-location: wdf\wdfusbtargetdeviceformatrequestforcycleport.htm
old-project: wdf
ms.assetid: f27dae6e-2fc7-4e26-84fb-4ce48da3db6b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_cc92bdd0-b899-41be-b9c6-c44e385ee001.xml, WdfUsbTargetDeviceFormatRequestForCyclePort, WdfUsbTargetDeviceFormatRequestForCyclePort method, kmdf.wdfusbtargetdeviceformatrequestforcycleport, wdf.wdfusbtargetdeviceformatrequestforcycleport, wdfusb/WdfUsbTargetDeviceFormatRequestForCyclePort
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
-	WdfUsbTargetDeviceFormatRequestForCyclePort
product:
- Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfUsbTargetDeviceFormatRequestForCyclePort function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfUsbTargetDeviceFormatRequestForCyclePort</b> method builds a power-cycle request for the port to which a specified device is attached, but it does not send the request.


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/hh439428">WdfUsbTargetDeviceCreateWithParameters</a>.


### -param Request [in]

A handle to a framework request object. For more information, see the following Remarks section.


## -returns



<b>WdfUsbTargetDeviceFormatRequestForCyclePort</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>
</td>
<td width="60%">
The device's USB device was unavailable.

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
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Use <b>WdfUsbTargetDeviceFormatRequestForCyclePort</b>, followed by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>, to send a power-cycle request either synchronously or asynchronously. Alternatively, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550080">WdfUsbTargetDeviceCyclePortSynchronously</a> method to send a request synchronously. 

Before the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>, it must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548680">WdfIoTargetStop</a> and it must <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">complete</a> or <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/canceling-i-o-requests">cancel</a> all I/O requests that it has sent to the I/O target. The driver must not send additional I/O requests to the I/O target until the cycle request completes.

You can forward an I/O request that your driver received in an I/O queue, or you can create and send a new request. 

To forward an I/O request that your driver received in an I/O queue, specify the received request's handle for the <b>WdfUsbTargetDeviceFormatRequestForCyclePort</b> method's <i>Request</i> parameter.

To create a new I/O request, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549951">WdfRequestCreate</a> to preallocate a request object. Supply the request handle for the <b>WdfUsbTargetDeviceFormatRequestForCyclePort</b> method's <i>Request</i> parameter. You can reuse the request object by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>. Your driver's <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function can preallocate request objects for a device.

After calling <b>WdfUsbTargetDeviceFormatRequestForCyclePort</b> to format an I/O request, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a> to send the request (either synchronously or asynchronously) to an I/O target. This call to <b>WdfRequestSend</b> must be made at IRQL = PASSIVE_LEVEL.

Multiple calls to <b>WdfUsbTargetDeviceFormatRequestForCyclePort</b> that use the same request do not cause additional resource allocations. Therefore, to reduce the chance that <a href="https://msdn.microsoft.com/library/windows/hardware/ff549951">WdfRequestCreate</a> will return STATUS_INSUFFICIENT_RESOURCES, your driver's <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function can call <b>WdfRequestCreate</b> to preallocate one or more request objects for a device. The driver can subsequently reuse (call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>), reformat (call <b>WdfUsbTargetDeviceFormatRequestForCyclePort</b>), and resend (call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>) each request object without risking a STATUS_INSUFFICIENT_RESOURCES return value from a later call to <b>WdfRequestCreate</b>. All subsequent calls to <b>WdfUsbTargetDeviceFormatRequestForCyclePort</b> for the reused request object will return STATUS_SUCCESS, if parameter values do not change. (If the driver does not call the same request-formatting method each time, additional resources might be allocated.)

For more information about the <b>WdfUsbTargetDeviceFormatRequestForCyclePort</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example formats a power-cycle request, registers a <a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a> callback function, and sends the request to an I/O target.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>status = WdfUsbTargetDeviceFormatRequestForCyclePort(
                                            UsbDevice,
                                            request
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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439428">WdfUsbTargetDeviceCreateWithParameters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550080">WdfUsbTargetDeviceCyclePortSynchronously</a>
 

 

