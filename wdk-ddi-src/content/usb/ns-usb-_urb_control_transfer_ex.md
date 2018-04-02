---
UID: NS:usb._URB_CONTROL_TRANSFER_EX
title: "_URB_CONTROL_TRANSFER_EX"
author: windows-driver-content
description: The _URB_CONTROL_TRANSFER_EX structure is used by USB client drivers to transfer data to or from a control pipe, with a timeout that limits the acceptable transfer time.
old-location: buses\_urb_control_transfer_ex.htm
old-project: usbref
ms.assetid: b77febb8-6428-4633-85a0-2f8c0409194d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: USBD_DEFAULT_PIPE_TRANSFER, USBD_SHORT_TRANSFER_OK, USBD_TRANSFER_DIRECTION_IN, USBD_TRANSFER_DIRECTION_OUT, _URB_CONTROL_TRANSFER_EX, _URB_CONTROL_TRANSFER_EX structure [Buses], buses._urb_control_transfer_ex, usb/_URB_CONTROL_TRANSFER_EX, usbstrct_08c90b6d-8b25-4ebe-9131-5d2a0bacd5db.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usb.h
req.include-header: Usb.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later operating systems.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usb.h
api_name:
-	_URB_CONTROL_TRANSFER_EX
product: Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# _URB_CONTROL_TRANSFER_EX structure


## -description


The <b>_URB_CONTROL_TRANSFER_EX</b> structure is used by USB client drivers to transfer data to or from a control pipe, with a timeout that limits the acceptable transfer time.


## -struct-fields




### -field Hdr

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540409">_URB_HEADER</a> structure that specifies the URB header information. <b>Hdr.Function</b> must be URB_FUNCTION_CONTROL_TRANSFER_EX, and <b>Hdr.Length</b> must be <code>sizeof(_URB_CONTROL_TRANSFER_EX)</code>.


### -field PipeHandle

Handle for the pipe.

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
Is set to direct the host controller not to return an error when it receives a packet from the device that is shorter than the maximum packet size for the endpoint. The maximum packet size for the endpoint is reported in the <b>bMaxPacketSize0</b> member  of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539280">USB_DEVICE_DESCRIPTOR</a> structure (device descriptor) for the default control endpoint. For a non-default control endpoint,  maximum packet size  is set in the <b>wMaxPacketSize</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539317">USB_ENDPOINT_DESCRIPTOR</a> structure (endpoint descriptor).

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


### -field Timeout

Indicates the time, in milliseconds, before the URB times out. A value of 0 indicates that there is no timeout for this URB. 


### -field Pad

Reserved. Do not use.


### -field hca

Reserved. Do not use.


### -field SetupPacket

Specifies a USB-defined request setup packet. The format of a USB request setup packet is found in the USB core specification.


## -remarks



This URB structure is identical to <a href="https://msdn.microsoft.com/library/windows/hardware/ff540384">_URB_CONTROL_TRANSFER</a>, except that the <b>Timeout</b> member establishes a timeout for the URB. 

The reserved members of this structure must be treated as opaque and are reserved for system use.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540384">_URB_CONTROL_TRANSFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540409">_URB_HEADER</a>
 

 

