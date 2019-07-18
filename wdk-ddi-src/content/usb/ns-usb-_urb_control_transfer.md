---
UID: NS:usb._URB_CONTROL_TRANSFER
title: _URB_CONTROL_TRANSFER (usb.h)
description: The _URB_CONTROL_TRANSFER structure is used by USB client drivers to transfer data to or from a control pipe.
old-location: buses\_urb_control_transfer.htm
tech.root: usbref
ms.assetid: ee557112-ada3-4906-a8f3-e59b59ab2bc1
ms.date: 05/07/2018
ms.keywords: USBD_DEFAULT_PIPE_TRANSFER, USBD_SHORT_TRANSFER_OK, USBD_TRANSFER_DIRECTION_IN, USBD_TRANSFER_DIRECTION_OUT, _URB_CONTROL_TRANSFER, _URB_CONTROL_TRANSFER structure [Buses], buses._urb_control_transfer, usb/_URB_CONTROL_TRANSFER, usbstrct_65d66cb6-2ce4-4eb2-ac3a-1cf68d3ad1b2.xml
ms.topic: struct
f1_keywords:
 - "usb/_URB_CONTROL_TRANSFER"
req.header: usb.h
req.include-header: Usb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
- usb.h
api_name:
- _URB_CONTROL_TRANSFER
product:
- Windows
targetos: Windows
req.typenames: 
---

# _URB_CONTROL_TRANSFER structure


## -description


The <b>_URB_CONTROL_TRANSFER</b> structure is used by USB client drivers to transfer data to or from a control pipe.


## -struct-fields




### -field Hdr

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_urb_header">_URB_HEADER</a> structure that specifies the URB header information. <b>Hdr.Function</b> must be URB_FUNCTION_CONTROL_TRANSFER, and <b>Hdr.Length</b> must be <code>sizeof(_URB_CONTROL_TRANSFER)</code>.


### -field PipeHandle

Handle for the control pipe.

 If target is the default control endpoint, then  <b>PipeHandle</b> must be <b>NULL</b>.  In this case, the <b>TransferFlags</b> must contain the USBD_DEFAULT_PIPE_TRANSFER flag.

If target is a non-default control endpoint, <b>PipeHandle</b> specifies an opaque handle for the control pipe. The host controller driver returns this handle when the client driver selects the device configuration with a URB of type URB_FUNCTION_SELECT_CONFIGURATION or when the client driver changes the settings for an interface with a URB of type URB_FUNCTION_SELECT_INTERFACE.   


### -field TransferFlags


Specifies zero, one, or a combination of the following flags:



<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="USBD_TRANSFER_DIRECTION_IN"></a><a id="usbd_transfer_direction_in"></a><dl>
<dt><b>USBD_TRANSFER_DIRECTION_IN</b></dt>
</dl>
</td>
<td width="60%">
Is set to request data from a device. To transfer data to a device, this flag must be clear. 

</td>
</tr>
<tr>
<td width="40%"><a id="USBD_TRANSFER_DIRECTION_OUT"></a><a id="usbd_transfer_direction_out"></a><dl>
<dt><b>USBD_TRANSFER_DIRECTION_OUT</b></dt>
</dl>
</td>
<td width="60%">
Is set to transfer data to a device. Setting this flag is equivalent to clearing the USBD_TRANSFER_DIRECTION_IN flag. 

</td>
</tr>
<tr>
<td width="40%"><a id="USBD_SHORT_TRANSFER_OK"></a><a id="usbd_short_transfer_ok"></a><dl>
<dt><b>USBD_SHORT_TRANSFER_OK</b></dt>
</dl>
</td>
<td width="60%">
Is set to direct the host controller not to return an error when it receives a packet from the device that is shorter than the maximum packet size for the endpoint. The maximum packet size for the endpoint is reported in the <b>bMaxPacketSize0</b> member  of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbspec/ns-usbspec-_usb_device_descriptor">USB_DEVICE_DESCRIPTOR</a> structure (device descriptor) for the default control endpoint. For a non-default control endpoint,  maximum packet size  is set in the <b>wMaxPacketSize</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbspec/ns-usbspec-_usb_endpoint_descriptor">USB_ENDPOINT_DESCRIPTOR</a> structure (endpoint descriptor).

When the host controller receives a packet whose length is shorter than the <b>wMaxPacketSize</b> value on a control endpoint, the behavior is as follows depending on the type of host controller:<ul>
<li>On EHCI host controllers, the host controller proceeds immediately to the status phase of the control transfer.  The transfer completes successfully, regardless of whether USBD_SHORT_TRANSFER_OK is set.

</li>
<li>On UHCI and OHCI host controllers, if USBD_SHORT_TRANSFER_OK is set, the host controller proceeds to the status phase.  If USBD_SHORT_TRANSFER_OK is not set, the host controller abandons the data and status phases of the control transfer and the transfer completes with an error.
</li>
</ul>


</td>
</tr>
<tr>
<td width="40%"><a id="USBD_DEFAULT_PIPE_TRANSFER"></a><a id="usbd_default_pipe_transfer"></a><dl>
<dt><b>USBD_DEFAULT_PIPE_TRANSFER</b></dt>
</dl>
</td>
<td width="60%">
Is set to direct the host controller to do a control transfer on the default  control pipe. This allows the caller to send commands to the default control pipe without explicitly specifying the pipe handle. 

</td>
</tr>
</table>
 


### -field TransferBufferLength

Specifies the length, in bytes, of the buffer specified in <b>TransferBuffer</b> or described in <b>TransferBufferMDL</b>. The host controller driver returns the number of bytes sent to or read from the pipe in this member.


### -field TransferBuffer

Pointer to a resident buffer for the transfer or is <b>NULL</b> if an MDL is supplied in <b>TransferBufferMDL</b>. The contents of this buffer depend on the value of <b>TransferFlags</b>. If USBD_TRANSFER_DIRECTION_IN is specified this buffer will contain data read from the device on return from the host controller driver. Otherwise, this buffer contains driver-supplied data for transfer to the device.


### -field TransferBufferMDL

Pointer to an MDL that describes a resident buffer or is <b>NULL</b> if a buffer is supplied in <b>TransferBuffer</b>. The contents of the buffer depend on the value of <b>TransferFlags</b>. If USBD_TRANSFER_DIRECTION_IN is specified, the described buffer will contain data read from the device on return from the host controller driver. Otherwise, the buffer contains driver-supplied data for transfer to the device. This MDL must be allocated from nonpaged pool.


### -field UrbLink

Reserved. Do not use.


### -field hca

Reserved. Do not use.


### -field SetupPacket

Specifies a USB-defined request setup packet. The format of a USB request setup packet is found in the USB core specification.


## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_urb_control_transfer_ex">URB_CONTROL_TRANSFER_EX</a> structure is identical to <b>URB_CONTROL_TRANSFER</b>, except that it provides a timeout value in the <b>Timeout</b> field.

The reserved members of this structure must be treated as opaque and are reserved for system use.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_urb">URB</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_urb_control_transfer_ex">URB_CONTROL_TRANSFER_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">USB Structures</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_urb_header">_URB_HEADER</a>
 

 

