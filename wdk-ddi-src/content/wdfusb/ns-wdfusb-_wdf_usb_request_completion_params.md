---
UID: NS:wdfusb._WDF_USB_REQUEST_COMPLETION_PARAMS
title: _WDF_USB_REQUEST_COMPLETION_PARAMS (wdfusb.h)
description: The WDF_USB_REQUEST_COMPLETION_PARAMS structure contains parameters that are associated with the completion of an I/O request for a USB device.
old-location: wdf\wdf_usb_request_completion_params.htm
tech.root: wdf
ms.assetid: cd29d27c-9da2-477f-898e-13ee480aac9e
ms.date: 02/26/2018
ms.keywords: "*PWDF_USB_REQUEST_COMPLETION_PARAMS, DFUsbRef_14574f86-fd65-41df-be8e-557f6fe09c4f.xml, PWDF_USB_REQUEST_COMPLETION_PARAMS, PWDF_USB_REQUEST_COMPLETION_PARAMS structure pointer, WDF_USB_REQUEST_COMPLETION_PARAMS, WDF_USB_REQUEST_COMPLETION_PARAMS structure, _WDF_USB_REQUEST_COMPLETION_PARAMS, kmdf.wdf_usb_request_completion_params, wdf.wdf_usb_request_completion_params, wdfusb/PWDF_USB_REQUEST_COMPLETION_PARAMS, wdfusb/WDF_USB_REQUEST_COMPLETION_PARAMS"
ms.topic: struct
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfusb.h
api_name:
- WDF_USB_REQUEST_COMPLETION_PARAMS
product:
- Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_COMPLETION_PARAMS, *PWDF_USB_REQUEST_COMPLETION_PARAMS
---

# _WDF_USB_REQUEST_COMPLETION_PARAMS structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_USB_REQUEST_COMPLETION_PARAMS</b> structure contains parameters that are associated with the completion of an I/O request for a USB device.


## -struct-fields




### -field UsbdStatus

The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff539136(v=vs.85)">USBD_STATUS</a>-typed status value that the I/O target returned.


### -field Type

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/ne-wdfusb-_wdf_usb_request_type">WDF_USB_REQUEST_TYPE</a>-typed values that identifies the request type.


### -field Parameters


### -field Parameters.DeviceString


### -field Parameters.DeviceString.Buffer

If the driver has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdeviceformatrequestforstring">WdfUsbTargetDeviceFormatRequestForString</a>, this member contains the driver-supplied handle to the memory object that receives the Unicode string.


### -field Parameters.DeviceString.LangID

If the driver has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdeviceformatrequestforstring">WdfUsbTargetDeviceFormatRequestForString</a>, this member contains the driver-supplied language identifier.


### -field Parameters.DeviceString.StringIndex

If the driver has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdeviceformatrequestforstring">WdfUsbTargetDeviceFormatRequestForString</a>, this member contains the driver-supplied string index.


### -field Parameters.DeviceString.RequiredSize

If the driver has called any method that <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/working-with-usb-devices">obtains a device's Unicode strings</a> (except <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdeviceformatrequestforurb">WdfUsbTargetDeviceFormatRequestForUrb</a>), this member contains the required size of the buffer that <b>Parameters.DeviceString.Buffer</b> specifies. 

If the driver called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdeviceformatrequestforurb">WdfUsbTargetDeviceFormatRequestForUrb</a>, it can obtain the required size value from the URB whose handle is in <b>Parameters.DeviceUrb.Buffer</b>.


### -field Parameters.DeviceControlTransfer


### -field Parameters.DeviceControlTransfer.Buffer

If the driver has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdeviceformatrequestforcontroltransfer">WdfUsbTargetDeviceFormatRequestForControlTransfer</a>, this member contains the driver-supplied handle to the memory object that receives input or output data.


### -field Parameters.DeviceControlTransfer.SetupPacket

If the driver has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdeviceformatrequestforcontroltransfer">WdfUsbTargetDeviceFormatRequestForControlTransfer</a>, this member contains the address of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/ns-wdfusb-_wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a> structure that the driver supplied.


### -field Parameters.DeviceControlTransfer.Length

If the driver has called any method that <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/working-with-usb-devices">sends a control transfer</a> (except <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdeviceformatrequestforurb">WdfUsbTargetDeviceFormatRequestForUrb</a>), this member contains the number of bytes that were sent or received. 

If the driver called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdeviceformatrequestforurb">WdfUsbTargetDeviceFormatRequestForUrb</a>, it can obtain the length value from the URB whose handle is in <b>Parameters.DeviceUrb.Buffer</b>.


### -field Parameters.DeviceUrb


### -field Parameters.DeviceUrb.Buffer

If the driver has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdeviceformatrequestforurb">WdfUsbTargetDeviceFormatRequestForUrb</a>, this member contains the driver-supplied handle to the memory object that contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_urb">URB</a> structure.


### -field Parameters.PipeWrite


### -field Parameters.PipeWrite.Buffer

If the driver has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetpipeformatrequestforwrite">WdfUsbTargetPipeFormatRequestForWrite</a>, this member contains the driver-supplied handle to the memory object that was written to the pipe.


### -field Parameters.PipeWrite.Length

If the driver has called any method <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/working-with-usb-pipes">that writes to a pipe</a> (except <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdeviceformatrequestforurb">WdfUsbTargetDeviceFormatRequestForUrb</a>), this member contains the number of bytes that were sent. 

If the driver called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdeviceformatrequestforurb">WdfUsbTargetDeviceFormatRequestForUrb</a>, it can obtain the length value from the URB whose handle is in <b>Parameters.PipeUrb.Buffer</b>.


### -field Parameters.PipeWrite.Offset

If the driver has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetpipeformatrequestforwrite">WdfUsbTargetPipeFormatRequestForWrite</a>, this member contains the driver-supplied buffer offset. 


### -field Parameters.PipeRead


### -field Parameters.PipeRead.Buffer

If the driver has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetpipeformatrequestforread">WdfUsbTargetPipeFormatRequestForRead</a>, this member contains the driver-supplied handle to the memory object that contains data that was read from the pipe.


### -field Parameters.PipeRead.Length

If the driver has called any method that <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/working-with-usb-pipes">reads from a pipe</a> sends a control transfer (except <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdeviceformatrequestforurb">WdfUsbTargetDeviceFormatRequestForUrb</a>), this member contains the number of bytes that were received. 

If the driver called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdeviceformatrequestforurb">WdfUsbTargetDeviceFormatRequestForUrb</a>, it can obtain the length value from the URB whose handle is in <b>Parameters.PipeUrb.Buffer</b>.


### -field Parameters.PipeRead.Offset

If the driver has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetpipeformatrequestforread">WdfUsbTargetPipeFormatRequestForRead</a>, this member contains the driver-supplied buffer offset. 


### -field Parameters.PipeUrb


### -field Parameters.PipeUrb.Buffer

If the driver has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetpipeformatrequestforurb">WdfUsbTargetPipeFormatRequestForUrb</a>, this member contains the driver-supplied handle to the memory object that contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_urb">URB</a> structure.


## -remarks



The <b>WDF_USB_REQUEST_COMPLETION_PARAMS</b> structure is a member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/ns-wdfrequest-_wdf_request_completion_params">WDF_REQUEST_COMPLETION_PARAMS</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nc-wdfrequest-evt_wdf_request_completion_routine">CompletionRoutine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/ns-wdfrequest-_wdf_request_completion_params">WDF_REQUEST_COMPLETION_PARAMS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestgetcompletionparams">WdfRequestGetCompletionParams</a>
 

 

