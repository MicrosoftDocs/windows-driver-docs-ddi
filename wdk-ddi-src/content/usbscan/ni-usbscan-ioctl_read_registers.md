---
UID: NI:usbscan.IOCTL_READ_REGISTERS
title: IOCTL_READ_REGISTERS
author: windows-driver-content
description: Reads from USB device registers, using the control pipe.
old-location: image\ioctl_read_registers.htm
old-project: image
ms.assetid: b54c9a15-0d48-4aff-98e5-1f0dfc070ed6
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
req.alt-api: IOCTL_READ_REGISTERS
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

# IOCTL_READ_REGISTERS IOCTL



## -description
Reads from USB device registers, using the control pipe.



## -ioctlparameters

### -input-buffer
Pointer to an <a href="..\usbscan\ns-usbscan-_io_block.md">IO_BLOCK</a> structure.


### -input-buffer-length
Size of the input buffer.


### -output-buffer
Pointer to a buffer to receive register contents.


### -output-buffer-length
Size of the output buffer. The value must match the contents of the <b>uLength</b> member of the IO_BLOCK structure.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks


Device handle, obtained by calling <a href="https://msdn.microsoft.com/80a96083-4de9-4422-9705-b8ad2b6cbd1b">CreateFile</a>.

IOCTL_READ_REGISTERS

Pointer to an <a href="..\usbscan\ns-usbscan-_io_block.md">IO_BLOCK</a> structure.

Size of the input buffer.

Pointer to a buffer to receive register contents.

Size of the output buffer. The value must match the contents of the <b>uLength</b> member of the IO_BLOCK structure.

Pointer to a location to receive the number of bytes returned.

Optional pointer to an OVERLAPPED structure (described in the Microsoft Windows SDK documentation).

When the <b>DeviceloControl</b> function is called with the IOCTL_READ_REGISTERS I/O control code, the caller must specify the address of an <a href="..\usbscan\ns-usbscan-_io_block.md">IO_BLOCK</a> structure as the function's <i>lpInBuffer</i> parameter.

Using the IO_BLOCK contents, the kernel-mode driver creates a <a href="..\usb\ns-usb-_urb.md">URB</a> that contains a <a href="..\usb\ns-usb-_urb_control_vendor_or_class_request.md">_URB_CONTROL_VENDOR_OR_CLASS_REQUEST</a> structure.

The following table indicates the values assigned to _URB_CONTROL_VENDOR_OR_CLASS_REQUEST structure members.

<b>TransferFlags</b>

1

<b>TransferBufferLength</b>

<i>pIoBlock</i>-&gt;<b>uLength</b>

<b>TransferBuffer</b>


<a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a>'s <i>lpOutBuffer</i> argument.

<b>TransferBufferMDL</b>

<b>NULL</b>

<b>RequestTypeReservedBits</b>

0xC0

<b>Request</b>

(<i>pIoBlock</i>-&gt;<b>uLength</b> &gt; 1) ? 0x04 : 0x0C

<b>Value</b>

(<b>SHORT</b>)<i>pIoBlock</i>-&gt;<b>uOffset</b>

<b>Index</b>

<i>pIoBlock</i>-&gt;<b>uIndex</b>

For more information, see <a href="https://msdn.microsoft.com/f9216d3c-4930-4c26-8eac-6ee500b038e0">Accessing Kernel-Mode Drivers for Still Image Devices</a>.</p>