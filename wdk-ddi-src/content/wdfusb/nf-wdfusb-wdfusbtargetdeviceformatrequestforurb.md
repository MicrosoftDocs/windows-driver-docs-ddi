---
UID: NF:wdfusb.WdfUsbTargetDeviceFormatRequestForUrb
title: WdfUsbTargetDeviceFormatRequestForUrb function (wdfusb.h)
description: The WdfUsbTargetDeviceFormatRequestForUrb method builds an USB request for a specified USB device, using request parameters that are described by a URB, but it does not send the request.
old-location: wdf\wdfusbtargetdeviceformatrequestforurb.htm
tech.root: wdf
ms.assetid: 886120f0-da2a-4a00-b440-ce1274c516d4
ms.date: 02/26/2018
keywords: ["WdfUsbTargetDeviceFormatRequestForUrb function"]
ms.keywords: DFUsbRef_c7b76463-570c-4f0d-b4d5-37ef192ba30f.xml, WdfUsbTargetDeviceFormatRequestForUrb, WdfUsbTargetDeviceFormatRequestForUrb method, kmdf.wdfusbtargetdeviceformatrequestforurb, wdf.wdfusbtargetdeviceformatrequestforurb, wdfusb/WdfUsbTargetDeviceFormatRequestForUrb
f1_keywords:
 - "wdfusb/WdfUsbTargetDeviceFormatRequestForUrb"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfUsbTargetDeviceFormatRequestForUrb
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetDeviceFormatRequestForUrb function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfUsbTargetDeviceFormatRequestForUrb</b> method builds an USB request for a specified USB device, using request parameters that are described by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a>, but it does not send the request.


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>.


### -param Request [in]

A handle to a framework request object. For more information, see the following Remarks section.


### -param UrbMemory [in]

A handle to a framework memory object that contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a> structure or one of the structure's union members. (All of the URB structure's union members contain the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_header">_URB_HEADER</a> structure.) 

If the driver previously called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a> to create <i>UsbDevice</i>, the driver must use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreateurb">WdfUsbTargetDeviceCreateUrb</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreateisochurb">WdfUsbTargetDeviceCreateIsochUrb</a> to create the URB contained in this memory object. Otherwise, a bug check occurs.


### -param UrbMemoryOffset [in, optional]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/ns-wdfmemory-_wdfmemory_offset">WDFMEMORY_OFFSET</a> structure that supplies optional byte offset and length values. The framework uses these values to determine the beginning address of the URB within the memory that <i>UrbMemory</i> specifies. If this pointer is <b>NULL</b>, the URB is located at the beginning of the <i>UrbMemory</i> memory. 


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
 

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Use <b>WdfUsbTargetDeviceFormatRequestForUrb</b>, followed by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsend">WdfRequestSend</a>, to send a USB control transfer request either synchronously or asynchronously. Alternatively, use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicesendurbsynchronously">WdfUsbTargetDeviceSendUrbSynchronously</a> method to send a request synchronously. 

You can forward an I/O request that your driver received in an I/O queue, or you can create and send a new request. 

To forward an I/O request that your driver received in an I/O queue, specify the received request's handle for the <b>WdfUsbTargetDeviceFormatRequestForUrb</b> method's <i>Request</i> parameter.

To create a new I/O request, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcreate">WdfRequestCreate</a> to preallocate a request object. Supply the request handle for the <b>WdfUsbTargetDeviceFormatRequestForUrb</b> method's <i>Request</i> parameter. You can reuse the request object by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestreuse">WdfRequestReuse</a>. Your driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function can preallocate request objects for a device.

After calling <b>WdfUsbTargetDeviceFormatRequestForUrb</b> to format an I/O request, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsend">WdfRequestSend</a> to send the request (either synchronously or asynchronously) to an I/O target. Do not use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_forward_options_flags">send and forget option</a> to send the request.

Multiple calls to <b>WdfUsbTargetDeviceFormatRequestForUrb</b> that use the same request do not cause additional resource allocations. Therefore, to reduce the chance that <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcreate">WdfRequestCreate</a> will return STATUS_INSUFFICIENT_RESOURCES, your driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function can call <b>WdfRequestCreate</b> to preallocate one or more request objects for a device. The driver can subsequently reuse (call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestreuse">WdfRequestReuse</a>), reformat (call <b>WdfUsbTargetDeviceFormatRequestForUrb</b>), and resend (call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsend">WdfRequestSend</a>) each request object without risking a STATUS_INSUFFICIENT_RESOURCES return value from a later call to <b>WdfRequestCreate</b>. All subsequent calls to <b>WdfUsbTargetDeviceFormatRequestForUrb</b> for the reused request object will return STATUS_SUCCESS, if parameter values do not change. (If the driver does not call the same request-formatting method each time, additional resources might be allocated.)

For information about obtaining status information after an I/O request completes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">Obtaining Completion Information</a>.

For more information about the <b>WdfUsbTargetDeviceFormatRequestForUrb</b> method and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example creates a memory object to hold a URB structure, initializes the URB structure, and calls <b>WdfUsbTargetDeviceFormatRequestForUrb</b> to format a request that uses the URB structure's contents. Then, the example registers a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_completion_routine">CompletionRoutine</a> callback function and sends the request to an I/O target.

```cpp
WDFMEMORY urbMemory;
URB *urbBuffer;

status = WdfMemoryCreate(
                         WDF_NO_OBJECT_ATTRIBUTES,
                         NonPagedPool,
                         0,
                         sizeof(struct _URB_CONTROL_GET_CONFIGURATION_REQUEST),
                         &urbMemory,
                         NULL
                         );

if (!NT_SUCCESS(status)){
    return status;
}
urbBuffer = (PURB) WdfMemoryGetBuffer(
                                      urbMemory,
                                      NULL
                                      );
urbBuffer->UrbHeader.Function =  URB_FUNCTION_GET_CONFIGURATION;
urbBuffer->UrbHeader.Length = sizeof(struct _URB_CONTROL_GET_CONFIGURATION_REQUEST);
urbBuffer->UrbControlGetConfigurationRequest.TransferBufferLength = 1 ;
urbBuffer->UrbControlGetConfigurationRequest.TransferBufferMDL = NULL;
urbBuffer->UrbControlGetConfigurationRequest.TransferBuffer = outBuffer;
urbBuffer->UrbControlGetConfigurationRequest.UrbLink = NULL;

status = WdfUsbTargetDeviceFormatRequestForUrb(
                                               deviceContext->WdfUsbTargetDevice,
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
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/ns-wdfmemory-_wdfmemory_offset">WDFMEMORY_OFFSET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestreuse">WdfRequestReuse</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsend">WdfRequestSend</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicesendurbsynchronously">WdfUsbTargetDeviceSendUrbSynchronously</a>
 

 

