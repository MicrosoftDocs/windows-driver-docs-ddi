---
UID: NF:wdfusb.WdfUsbTargetDeviceFormatRequestForCyclePort
title: WdfUsbTargetDeviceFormatRequestForCyclePort function
author: windows-driver-content
description: The WdfUsbTargetDeviceFormatRequestForCyclePort method builds a power-cycle request for the port to which a specified device is attached, but it does not send the request.
old-location: wdf\wdfusbtargetdeviceformatrequestforcycleport.htm
old-project: wdf
ms.assetid: f27dae6e-2fc7-4e26-84fb-4ce48da3db6b
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfusb/WdfUsbTargetDeviceFormatRequestForCyclePort, PFN_WDFUSBTARGETDEVICEFORMATREQUESTFORCYCLEPORT, wdf.wdfusbtargetdeviceformatrequestforcycleport, WdfUsbTargetDeviceFormatRequestForCyclePort, WdfUsbTargetDeviceFormatRequestForCyclePort method, kmdf.wdfusbtargetdeviceformatrequestforcycleport, DFUsbRef_cc92bdd0-b899-41be-b9c6-c44e385ee001.xml
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
-	WdfUsbTargetDeviceFormatRequestForCyclePort
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfUsbTargetDeviceFormatRequestForCyclePort function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfUsbTargetDeviceFormatRequestForCyclePort</b> method builds a power-cycle request for the port to which a specified device is attached, but it does not send the request.


## -syntax


````
NTSTATUS WdfUsbTargetDeviceFormatRequestForCyclePort(
  _In_ WDFUSBDEVICE UsbDevice,
  _In_ WDFREQUEST   Request
);
````


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>.


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


Use <b>WdfUsbTargetDeviceFormatRequestForCyclePort</b>, followed by <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>, to send a power-cycle request either synchronously or asynchronously. Alternatively, use the <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecycleportsynchronously.md">WdfUsbTargetDeviceCyclePortSynchronously</a> method to send a request synchronously. 

Before the driver calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>, it must call <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstop.md">WdfIoTargetStop</a> and it must <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">complete</a> or <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/canceling-i-o-requests">cancel</a> all I/O requests that it has sent to the I/O target. The driver must not send additional I/O requests to the I/O target until the cycle request completes.

You can forward an I/O request that your driver received in an I/O queue, or you can create and send a new request. 

To forward an I/O request that your driver received in an I/O queue, specify the received request's handle for the <b>WdfUsbTargetDeviceFormatRequestForCyclePort</b> method's <i>Request</i> parameter.

To create a new I/O request, call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a> to preallocate a request object. Supply the request handle for the <b>WdfUsbTargetDeviceFormatRequestForCyclePort</b> method's <i>Request</i> parameter. You can reuse the request object by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>. Your driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function can preallocate request objects for a device.

After calling <b>WdfUsbTargetDeviceFormatRequestForCyclePort</b> to format an I/O request, the driver must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a> to send the request (either synchronously or asynchronously) to an I/O target. This call to <b>WdfRequestSend</b> must be made at IRQL = PASSIVE_LEVEL.

Multiple calls to <b>WdfUsbTargetDeviceFormatRequestForCyclePort</b> that use the same request do not cause additional resource allocations. Therefore, to reduce the chance that <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a> will return STATUS_INSUFFICIENT_RESOURCES, your driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function can call <b>WdfRequestCreate</b> to preallocate one or more request objects for a device. The driver can subsequently reuse (call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>), reformat (call <b>WdfUsbTargetDeviceFormatRequestForCyclePort</b>), and resend (call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>) each request object without risking a STATUS_INSUFFICIENT_RESOURCES return value from a later call to <b>WdfRequestCreate</b>. All subsequent calls to <b>WdfUsbTargetDeviceFormatRequestForCyclePort</b> for the reused request object will return STATUS_SUCCESS, if parameter values do not change. (If the driver does not call the same request-formatting method each time, additional resources might be allocated.)

For more information about the <b>WdfUsbTargetDeviceFormatRequestForCyclePort</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.



## -see-also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecycleportsynchronously.md">WdfUsbTargetDeviceCyclePortSynchronously</a>

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>

<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetDeviceFormatRequestForCyclePort method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

