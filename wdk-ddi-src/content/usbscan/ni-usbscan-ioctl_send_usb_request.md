---
UID: NI:usbscan.IOCTL_SEND_USB_REQUEST
title: IOCTL_SEND_USB_REQUEST
author: windows-driver-content
description: Sends a vendor-defined request to a USB device, using the control pipe, and optionally sends or receives additional data.
old-location: image\ioctl_send_usb_request.htm
old-project: image
ms.assetid: 27e22a21-cd89-43e8-8ce1-448c0f4c4d78
ms.author: windowsdriverdev
ms.date: 1/17/2018
ms.keywords: _RAW_PIPE_TYPE, RAW_PIPE_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbscan.h
req.include-header: Usbscan.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_SEND_USB_REQUEST
req.alt-loc: Usbscan.h
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
req.typenames: RAW_PIPE_TYPE
req.product: Windows 10 or later.
---

# IOCTL_SEND_USB_REQUEST IOCTL



## -description

Sends a vendor-defined request to a USB device, using the control pipe, and optionally sends or receives additional data.



Sends a vendor-defined request to a USB device, using the control pipe, and optionally sends or receives additional data.



## -ioctlparameters

### -input-buffer
Pointer to an <a href="..\usbscan\ns-usbscan-_io_block_ex.md">IO_BLOCK_EX</a> structure.


### -input-buffer-length
Size of the input buffer.


### -output-buffer
Pointer to the same buffer the <b>pbyData</b> member of the IO_BLOCK_EX structure identified, or <b>NULL</b> if a data transfer is not being requested.


### -output-buffer-length
Size of the output buffer, or zero if a data transfer is not being requested.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks


Device handle, obtained by calling <a href="https://msdn.microsoft.com/80a96083-4de9-4422-9705-b8ad2b6cbd1b">CreateFile</a>.

IOCTL_SEND_USB_REQUEST

Pointer to an <a href="..\usbscan\ns-usbscan-_io_block_ex.md">IO_BLOCK_EX</a> structure.

Size of the input buffer.

Pointer to the same buffer the <b>pbyData</b> member of the IO_BLOCK_EX structure identified, or <b>NULL</b> if a data transfer is not being requested.

Size of the output buffer, or zero if a data transfer is not being requested.

Pointer to a location to receive the number of bytes returned.

Optional pointer to an OVERLAPPED structure (described in the Microsoft Windows SDK documentation).

When the <b>DeviceloControl</b> function is called with the IOCTL_SEND_USB_REQUEST control code, the caller must specify the address of an <a href="..\usbscan\ns-usbscan-_io_block_ex.md">IO_BLOCK_EX</a> structure as the function's <i>lpInBuffer</i> parameter. The type of request specified with this I/O control code is device-specific and vendor-defined, as are the type and size of any information that might be sent or received.

The following table shows how input arguments should be specified.

<i>lpInBuffer</i>

IO_BLOCK_EX pointer.

<i>lpOutBuffer</i>

Pointer to buffer that will receive data to be read.

Pointer to buffer containing data to be written.

<b>NULL</b>

<i>lpOutBufferSize</i>

Size of buffer.

Zero

<b>bRequest</b> member of IO_BLOCK_EX structure

Device-specific request code.

<b>pbyData</b> member of IO_BLOCK_EX structure

Same pointer as <i>lpOutBuffer</i>.

<b>uLength</b> member of IO_BLOCK_EX structure

Same value as <i>lpOutBufferSize</i>.

<b>fTransferDirectionIn</b> member of IO_BLOCK_EX structure

<b>TRUE</b>

<b>FALSE</b>

Note that the <b>bmRequestType</b> member of the IO_BLOCK_EX structure is not used with IOCTL_SEND_USB_REQUEST.

Using the <a href="..\usbscan\ns-usbscan-_io_block_ex.md">IO_BLOCK_EX</a> structure contents, the kernel-mode driver creates a <a href="..\usb\ns-usb-_urb.md">URB</a> that contains a <a href="..\usb\ns-usb-_urb_control_vendor_or_class_request.md">_URB_CONTROL_VENDOR_OR_CLASS_REQUEST</a> structure.

The following table indicates the values assigned to _URB_CONTROL_VENDOR_OR_CLASS_REQUEST structure members.

<b>TransferFlags</b>

0

<b>TransferBufferLength</b>

<i>pIoBlockEx</i>-&gt;<b>uLength</b>

<b>TransferBuffer</b>

<i>lpOutBuffer</i> (read) or

<i>pIoBlockEx</i>-&gt;<b>pbyData</b> (write)

<b>TransferBufferMDL</b>

<b>RequestTypeReservedBits</b>

0xC0 (read) or

0x40 (write)

<b>Request</b>

<i>pIoBlockEx</i>-&gt;<b>bRequest</b>

<b>Value</b>

(<b>SHORT</b>)<i>pIoBlockEx</i>-&gt;<b>uOffset</b>

<b>Index</b>

<i>pIoBlockEx</i>-&gt;<b>uIndex</b>

For more information, see <a href="https://msdn.microsoft.com/f9216d3c-4930-4c26-8eac-6ee500b038e0">Accessing Kernel-Mode Drivers for Still Image Devices</a>.</p>