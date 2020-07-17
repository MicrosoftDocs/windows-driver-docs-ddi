---
UID: NI:usbscan.IOCTL_READ_REGISTERS
title: IOCTL_READ_REGISTERS (usbscan.h)
description: Reads from USB device registers, using the control pipe.
old-location: image\ioctl_read_registers.htm
tech.root: image
ms.assetid: b54c9a15-0d48-4aff-98e5-1f0dfc070ed6
ms.date: 05/03/2018
keywords: ["IOCTL_READ_REGISTERS IOCTL"]
ms.keywords: IOCTL_READ_REGISTERS, IOCTL_READ_REGISTERS control, IOCTL_READ_REGISTERS control code [Imaging Devices], image.ioctl_read_registers, stifnc_68af86d1-7d3b-4d2c-a5af-983f0339d71f.xml, usbscan/IOCTL_READ_REGISTERS
f1_keywords:
 - "usbscan/IOCTL_READ_REGISTERS"
 - "IOCTL_READ_REGISTERS"
req.header: usbscan.h
req.include-header: Usbscan.h
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
- Usbscan.h
api_name:
- IOCTL_READ_REGISTERS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_READ_REGISTERS IOCTL


## -description


Reads from USB device registers, using the control pipe.


## -ioctlparameters




### -input-buffer

Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbscan/ns-usbscan-_io_block">IO_BLOCK</a> structure.


### -input-buffer-length

Size of the input buffer.


### -output-buffer

Pointer to a buffer to receive register contents.


### -output-buffer-length

Size of the output buffer. The value must match the contents of the <b>uLength</b> member of the IO_BLOCK structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -remarks



<h3><a id="ddk_ioctl_read_registers_si"></a><a id="DDK_IOCTL_READ_REGISTERS_SI"></a>DeviceIoControl Parameters</h3>


When the <b>DeviceloControl</b> function is called with the IOCTL_READ_REGISTERS I/O control code, the caller must specify the address of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbscan/ns-usbscan-_io_block">IO_BLOCK</a> structure as the function's <i>lpInBuffer</i> parameter.

Using the IO_BLOCK contents, the kernel-mode driver creates a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a> that contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_control_vendor_or_class_request">_URB_CONTROL_VENDOR_OR_CLASS_REQUEST</a> structure.

The following table indicates the values assigned to _URB_CONTROL_VENDOR_OR_CLASS_REQUEST structure members.

<table>
<tr>
<th>Structure Member</th>
<th>Value Assigned</th>
</tr>
<tr>
<td>
<b>TransferFlags</b>

</td>
<td>
1

</td>
</tr>
<tr>
<td>
<b>TransferBufferLength</b>

</td>
<td>
<i>pIoBlock</i>-><b>uLength</b>

</td>
</tr>
<tr>
<td>
<b>TransferBuffer</b>

</td>
<td>

<a href="https://docs.microsoft.com/windows/desktop/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a>'s <i>lpOutBuffer</i> argument.

</td>
</tr>
<tr>
<td>
<b>TransferBufferMDL</b>

</td>
<td>
<b>NULL</b>

</td>
</tr>
<tr>
<td>
<b>RequestTypeReservedBits</b>

</td>
<td>
0xC0

</td>
</tr>
<tr>
<td>
<b>Request</b>

</td>
<td>
(<i>pIoBlock</i>-><b>uLength</b> > 1) ? 0x04 : 0x0C

</td>
</tr>
<tr>
<td>
<b>Value</b>

</td>
<td>
(<b>SHORT</b>)<i>pIoBlock</i>-><b>uOffset</b>

</td>
</tr>
<tr>
<td>
<b>Index</b>

</td>
<td>
<i>pIoBlock</i>-><b>uIndex</b>

</td>
</tr>
</table>
 

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/image/accessing-kernel-mode-drivers-for-still-image-devices">Accessing Kernel-Mode Drivers for Still Image Devices</a>.



