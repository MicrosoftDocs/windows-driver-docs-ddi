---
UID: NS:wdfusb._WDF_USB_REQUEST_COMPLETION_PARAMS
title: _WDF_USB_REQUEST_COMPLETION_PARAMS
author: windows-driver-content
description: The WDF_USB_REQUEST_COMPLETION_PARAMS structure contains parameters that are associated with the completion of an I/O request for a USB device.
old-location: wdf\wdf_usb_request_completion_params.htm
old-project: wdf
ms.assetid: cd29d27c-9da2-477f-898e-13ee480aac9e
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WDF_USB_REQUEST_COMPLETION_PARAMS, *PWDF_USB_REQUEST_COMPLETION_PARAMS, WDF_USB_REQUEST_COMPLETION_PARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_USB_REQUEST_COMPLETION_PARAMS
req.alt-loc: wdfusb.h
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
req.typenames: *PWDF_USB_REQUEST_COMPLETION_PARAMS, WDF_USB_REQUEST_COMPLETION_PARAMS
req.product: Windows 10 or later.
---

# _WDF_USB_REQUEST_COMPLETION_PARAMS structure



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_REQUEST_COMPLETION_PARAMS</b> structure contains parameters that are associated with the completion of an I/O request for a USB device.



## -syntax

````
typedef struct _WDF_USB_REQUEST_COMPLETION_PARAMS {
  USBD_STATUS          UsbdStatus;
  WDF_USB_REQUEST_TYPE Type;
  union {
    struct {
      WDFMEMORY Buffer;
      USHORT    LangID;
      UCHAR     StringIndex;
      UCHAR     RequiredSize;
    } DeviceString;
    struct {
      WDFMEMORY                    Buffer;
      WDF_USB_CONTROL_SETUP_PACKET SetupPacket;
      ULONG                        Length;
    } DeviceControlTransfer;
    struct {
      WDFMEMORY Buffer;
    } DeviceUrb;
    struct {
      WDFMEMORY Buffer;
      size_t    Length;
      size_t    Offset;
    } PipeWrite;
    struct {
      WDFMEMORY Buffer;
      size_t    Length;
      size_t    Offset;
    } PipeRead;
    struct {
      WDFMEMORY Buffer;
    } PipeUrb;
  } Parameters;
} WDF_USB_REQUEST_COMPLETION_PARAMS, *PWDF_USB_REQUEST_COMPLETION_PARAMS;
````


## -struct-fields

### -field UsbdStatus

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff539136">USBD_STATUS</a>-typed status value that the I/O target returned.


### -field Type

A <a href="..\wudfusb\ne-wudfusb-_wdf_usb_request_type.md">WDF_USB_REQUEST_TYPE</a>-typed values that identifies the request type.


### -field Parameters


### -field DeviceString


### -field Buffer

If the driver has called <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceformatrequestforstring.md">WdfUsbTargetDeviceFormatRequestForString</a>, this member contains the driver-supplied handle to the memory object that receives the Unicode string.


### -field LangID

If the driver has called <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceformatrequestforstring.md">WdfUsbTargetDeviceFormatRequestForString</a>, this member contains the driver-supplied language identifier.


### -field StringIndex

If the driver has called <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceformatrequestforstring.md">WdfUsbTargetDeviceFormatRequestForString</a>, this member contains the driver-supplied string index.


### -field RequiredSize

If the driver has called any method that <a href="wdf.working_with_usb_devices#obtaining_a_device_s_unicode_strings#obtaining_a_device_s_unicode_strings">obtains a device's Unicode strings</a> (except <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceformatrequestforurb.md">WdfUsbTargetDeviceFormatRequestForUrb</a>), this member contains the required size of the buffer that <b>Parameters.DeviceString.Buffer</b> specifies. 

If the driver called <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceformatrequestforurb.md">WdfUsbTargetDeviceFormatRequestForUrb</a>, it can obtain the required size value from the URB whose handle is in <b>Parameters.DeviceUrb.Buffer</b>.

</dd>
</dl>

### -field DeviceControlTransfer


### -field Buffer

If the driver has called <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceformatrequestforcontroltransfer.md">WdfUsbTargetDeviceFormatRequestForControlTransfer</a>, this member contains the driver-supplied handle to the memory object that receives input or output data.


### -field SetupPacket

If the driver has called <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceformatrequestforcontroltransfer.md">WdfUsbTargetDeviceFormatRequestForControlTransfer</a>, this member contains the address of the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a> structure that the driver supplied.


### -field Length

If the driver has called any method that <a href="wdf.working_with_usb_devices#sending_a_control_transfer#sending_a_control_transfer">sends a control transfer</a> (except <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceformatrequestforurb.md">WdfUsbTargetDeviceFormatRequestForUrb</a>), this member contains the number of bytes that were sent or received. 

If the driver called <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceformatrequestforurb.md">WdfUsbTargetDeviceFormatRequestForUrb</a>, it can obtain the length value from the URB whose handle is in <b>Parameters.DeviceUrb.Buffer</b>.

</dd>
</dl>

### -field DeviceUrb


### -field Buffer

If the driver has called <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceformatrequestforurb.md">WdfUsbTargetDeviceFormatRequestForUrb</a>, this member contains the driver-supplied handle to the memory object that contains a <a href="..\usb\ns-usb-_urb.md">URB</a> structure.

</dd>
</dl>

### -field PipeWrite


### -field Buffer

If the driver has called <a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipeformatrequestforwrite.md">WdfUsbTargetPipeFormatRequestForWrite</a>, this member contains the driver-supplied handle to the memory object that was written to the pipe.


### -field Length

If the driver has called any method <a href="wdf.working_with_usb_pipes#writing_to_a_pipe#writing_to_a_pipe">that writes to a pipe</a> (except <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceformatrequestforurb.md">WdfUsbTargetDeviceFormatRequestForUrb</a>), this member contains the number of bytes that were sent. 

If the driver called <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceformatrequestforurb.md">WdfUsbTargetDeviceFormatRequestForUrb</a>, it can obtain the length value from the URB whose handle is in <b>Parameters.PipeUrb.Buffer</b>.


### -field Offset

If the driver has called <a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipeformatrequestforwrite.md">WdfUsbTargetPipeFormatRequestForWrite</a>, this member contains the driver-supplied buffer offset. 

</dd>
</dl>

### -field PipeRead


### -field Buffer

If the driver has called <a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipeformatrequestforread.md">WdfUsbTargetPipeFormatRequestForRead</a>, this member contains the driver-supplied handle to the memory object that contains data that was read from the pipe.


### -field Length

If the driver has called any method that <a href="wdf.working_with_usb_pipes#reading_from_a_pipe#reading_from_a_pipe">reads from a pipe</a> sends a control transfer (except <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceformatrequestforurb.md">WdfUsbTargetDeviceFormatRequestForUrb</a>), this member contains the number of bytes that were received. 

If the driver called <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceformatrequestforurb.md">WdfUsbTargetDeviceFormatRequestForUrb</a>, it can obtain the length value from the URB whose handle is in <b>Parameters.PipeUrb.Buffer</b>.


### -field Offset

If the driver has called <a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipeformatrequestforread.md">WdfUsbTargetPipeFormatRequestForRead</a>, this member contains the driver-supplied buffer offset. 

</dd>
</dl>

### -field PipeUrb


### -field Buffer

If the driver has called <a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipeformatrequestforurb.md">WdfUsbTargetPipeFormatRequestForUrb</a>, this member contains the driver-supplied handle to the memory object that contains a <a href="..\usb\ns-usb-_urb.md">URB</a> structure.

</dd>
</dl>
</dd>
</dl>

## -remarks
The <b>WDF_USB_REQUEST_COMPLETION_PARAMS</b> structure is a member of the <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_completion_params.md">WDF_REQUEST_COMPLETION_PARAMS</a> structure.


## -see-also
<dl>
<dt>
<a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a>
</dt>
<dt>
<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_completion_params.md">WDF_REQUEST_COMPLETION_PARAMS</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetcompletionparams.md">WdfRequestGetCompletionParams</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_REQUEST_COMPLETION_PARAMS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

