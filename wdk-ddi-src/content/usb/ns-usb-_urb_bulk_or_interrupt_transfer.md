---
UID: NS:usb._URB_BULK_OR_INTERRUPT_TRANSFER
title: "_URB_BULK_OR_INTERRUPT_TRANSFER" (usb.h)
description: The _URB_BULK_OR_INTERRUPT_TRANSFER structure is used by USB client drivers to send or receive data on a bulk pipe or on an interrupt pipe.
old-location: buses\_urb_bulk_or_interrupt_transfer.htm
tech.root: usbref
ms.assetid: 398f50ad-4c58-4585-8fb8-c523b74793e9
ms.date: 05/07/2018
ms.keywords: USBD_SHORT_TRANSFER_OK, USBD_TRANSFER_DIRECTION_IN, USBD_TRANSFER_DIRECTION_OUT, _URB_BULK_OR_INTERRUPT_TRANSFER, _URB_BULK_OR_INTERRUPT_TRANSFER structure [Buses], buses._urb_bulk_or_interrupt_transfer, usb/_URB_BULK_OR_INTERRUPT_TRANSFER, usbstrct_3d3da976-5136-4648-850e-c0e3fe0999d8.xml
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usb.h
api_name:
-	_URB_BULK_OR_INTERRUPT_TRANSFER
product:
- Windows
targetos: Windows
req.typenames: 
---

# _URB_BULK_OR_INTERRUPT_TRANSFER structure


## -description


The <b>_URB_BULK_OR_INTERRUPT_TRANSFER</b> structure is used by USB client drivers to send or receive data on a bulk pipe or on an interrupt pipe.


## -struct-fields




### -field Hdr

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540409">_URB_HEADER</a> structure that specifies the URB header information. <b>Hdr.Function</b> must be URB_FUNCTION_BULK_OR_INTERRUPT_TRANSFER, and <b>Hdr.Length</b> must be set to <code>sizeof(_URB_BULK_OR_INTERRUPT_TRANSFER)</code>.


### -field PipeHandle

Specifies an opaque handle to the bulk or interrupt pipe. The host controller driver returns this handle when the client driver selects the device configuration with a URB of type URB_FUNCTION_SELECT_CONFIGURATION or when the client driver changes the settings for an interface with a URB of type URB_FUNCTION_SELECT_INTERFACE.  


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
Is set to direct the host controller not to return an error when it receives a packet from the device that is shorter than the maximum packet size for the endpoint. The maximum packet size for the endpoint is reported in the <b>wMaxPacketSize</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539317">USB_ENDPOINT_DESCRIPTOR</a> structure (endpoint descriptor). When  the host controller receives a packet shorter than <b>wMaxPacketSize</b> on a bulk or an interrupt endpoint, the host controller immediately stops requesting data from the endpoint and completes the transfer.  If the USBD_SHORT_TRANSFER_OK flag is not set, the host controller completes the transfer  with an error. 

This flag should not be set unless USBD_TRANSFER_DIRECTION_IN is also set. <b>Note</b>  On EHCI host controllers,  USBD_SHORT_TRANSFER_OK is ignored for bulk and interrupt endpoints.  Transfer of short packets on EHCI controllers does not result in an error condition. <p class="note">On UHCI and OHCI host controllers,   if USBD_SHORT_TRANSFER_OK is not set for a bulk or interrupt transfer, a short packet transfer halts the endpoint and an error code is returned for the transfer.  The client driver must resume the endpoint by submitting a URB_FUNCTION_SYNC_RESET_PIPE_AND_CLEAR_STALL request before submitting a transfer request to the endpoint.





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


## -remarks



Drivers can use the <b>UsbBuildInterruptOrBulkTransferRequest</b> service routine to format this URB. Buffers specified in <b>TransferBuffer</b> or described in <b>TransferBufferMDL </b>must be nonpageable. 

In an <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a>, both <b>TransferBuffer</b> and <b>TransferBufferMDL</b> parameters can be non-NULL values, at the same time. In that case, the transfer buffer and the MDL pointed to <b>TransferBuffer</b> and <b>TransferBufferMDL</b> must point to the same  buffer.

The USB bus driver processes this URB at DISPATCH_LEVEL.

The reserved members of this structure must be treated as opaque and are reserved for system use.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540409">_URB_HEADER</a>
 

 

