---
UID: NF:wdfusb.WdfUsbTargetDeviceFormatRequestForUrb
title: WdfUsbTargetDeviceFormatRequestForUrb function
author: windows-driver-content
description: The WdfUsbTargetDeviceFormatRequestForUrb method builds an USB request for a specified USB device, using request parameters that are described by a URB, but it does not send the request.
old-location: wdf\wdfusbtargetdeviceformatrequestforurb.htm
old-project: wdf
ms.assetid: 886120f0-da2a-4a00-b440-ce1274c516d4
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfUsbTargetDeviceFormatRequestForUrb, WdfUsbTargetDeviceFormatRequestForUrb method, DFUsbRef_c7b76463-570c-4f0d-b4d5-37ef192ba30f.xml, wdf.wdfusbtargetdeviceformatrequestforurb, kmdf.wdfusbtargetdeviceformatrequestforurb, wdfusb/WdfUsbTargetDeviceFormatRequestForUrb, PFN_WDFUSBTARGETDEVICEFORMATREQUESTFORURB
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfUsbTargetDeviceFormatRequestForUrb
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfUsbTargetDeviceFormatRequestForUrb function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfUsbTargetDeviceFormatRequestForUrb</b> method builds an USB request for a specified USB device, using request parameters that are described by a <a href="..\usb\ns-usb-_urb.md">URB</a>, but it does not send the request.


## -syntax


````
NTSTATUS WdfUsbTargetDeviceFormatRequestForUrb(
  _In_     WDFUSBDEVICE      UsbDevice,
  _In_     WDFREQUEST        Request,
  _In_     WDFMEMORY         UrbMemory,
  _In_opt_ PWDFMEMORY_OFFSET UrbMemoryOffset
);
````


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>.


### -param Request [in]

A handle to a framework request object. For more information, see the following Remarks section.


### -param UrbMemory [in]

A handle to a framework memory object that contains a <a href="..\usb\ns-usb-_urb.md">URB</a> structure or one of the structure's union members. (All of the URB structure's union members contain the <a href="..\usb\ns-usb-_urb_header.md">_URB_HEADER</a> structure.) 

If the driver previously called <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a> to create <i>UsbDevice</i>, the driver must use <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreateurb.md">WdfUsbTargetDeviceCreateUrb</a> or <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreateisochurb.md">WdfUsbTargetDeviceCreateIsochUrb</a> to create the URB contained in this memory object. Otherwise, a bug check occurs.


### -param UrbMemoryOffset [in, optional]

A pointer to a caller-allocated <a href="..\wudfddi_types\ns-wudfddi_types-_wdfmemory_offset.md">WDFMEMORY_OFFSET</a> structure that supplies optional byte offset and length values. The framework uses these values to determine the beginning address of the URB within the memory that <i>UrbMemory</i> specifies. If this pointer is <b>NULL</b>, the URB is located at the beginning of the <i>UrbMemory</i> memory. 


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


Use <b>WdfUsbTargetDeviceFormatRequestForUrb</b>, followed by <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>, to send a USB control transfer request either synchronously or asynchronously. Alternatively, use the <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicesendurbsynchronously.md">WdfUsbTargetDeviceSendUrbSynchronously</a> method to send a request synchronously. 

You can forward an I/O request that your driver received in an I/O queue, or you can create and send a new request. 

To forward an I/O request that your driver received in an I/O queue, specify the received request's handle for the <b>WdfUsbTargetDeviceFormatRequestForUrb</b> method's <i>Request</i> parameter.

To create a new I/O request, call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a> to preallocate a request object. Supply the request handle for the <b>WdfUsbTargetDeviceFormatRequestForUrb</b> method's <i>Request</i> parameter. You can reuse the request object by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>. Your driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function can preallocate request objects for a device.

After calling <b>WdfUsbTargetDeviceFormatRequestForUrb</b> to format an I/O request, the driver must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a> to send the request (either synchronously or asynchronously) to an I/O target. Do not use the <a href="..\wdfrequest\ne-wdfrequest-_wdf_request_forward_options_flags.md">send and forget option</a> to send the request.

Multiple calls to <b>WdfUsbTargetDeviceFormatRequestForUrb</b> that use the same request do not cause additional resource allocations. Therefore, to reduce the chance that <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a> will return STATUS_INSUFFICIENT_RESOURCES, your driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function can call <b>WdfRequestCreate</b> to preallocate one or more request objects for a device. The driver can subsequently reuse (call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>), reformat (call <b>WdfUsbTargetDeviceFormatRequestForUrb</b>), and resend (call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>) each request object without risking a STATUS_INSUFFICIENT_RESOURCES return value from a later call to <b>WdfRequestCreate</b>. All subsequent calls to <b>WdfUsbTargetDeviceFormatRequestForUrb</b> for the reused request object will return STATUS_SUCCESS, if parameter values do not change. (If the driver does not call the same request-formatting method each time, additional resources might be allocated.)

For information about obtaining status information after an I/O request completes, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">Obtaining Completion Information</a>.

For more information about the <b>WdfUsbTargetDeviceFormatRequestForUrb</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.



## -see-also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>

<a href="..\wudfddi_types\ns-wudfddi_types-_wdfmemory_offset.md">WDFMEMORY_OFFSET</a>

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicesendurbsynchronously.md">WdfUsbTargetDeviceSendUrbSynchronously</a>

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>

<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetDeviceFormatRequestForUrb method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

