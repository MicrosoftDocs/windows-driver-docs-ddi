---
UID: NI:hidclass.IOCTL_GET_PHYSICAL_DESCRIPTOR
title: IOCTL_GET_PHYSICAL_DESCRIPTOR (hidclass.h)
description: The IOCTL_GET_PHYSICAL_DESCRIPTOR request obtains the physical descriptor of a top-level collection. For a minidriver, this descriptor is the descriptor of the HIDClass device.
old-location: hid\ioctl_get_physical_descriptor.htm
tech.root: hid
ms.assetid: cf15dd7f-4568-40c7-b2e4-7cec8239df0b
ms.date: 04/30/2018
ms.keywords: IOCTL_GET_PHYSICAL_DESCRIPTOR, IOCTL_GET_PHYSICAL_DESCRIPTOR control, IOCTL_GET_PHYSICAL_DESCRIPTOR control code [Human Input Devices], hid.ioctl_get_physical_descriptor, hidclass/IOCTL_GET_PHYSICAL_DESCRIPTOR, hidioreq_3a61c6d2-a97a-47d6-86b1-317e22775271.xml
ms.topic: ioctl
req.header: hidclass.h
req.include-header: Hidclass.h
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
- hidclass.h
api_name:
- IOCTL_GET_PHYSICAL_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_GET_PHYSICAL_DESCRIPTOR IOCTL


## -description


The IOCTL_GET_PHYSICAL_DESCRIPTOR request obtains the physical descriptor of a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>. For a minidriver, this descriptor is the descriptor of the HIDClass device.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 


## -ioctlparameters




### -input-buffer

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer. 


### -input-buffer-length








### -output-buffer

<b>Irp-&gt;MdlAddress</b> must point to the buffer that will receive the physical descriptor. 

The HID minidriver copies the physical descriptor into the user buffer at <b>Irp-&gt;UserBuffer</b>.


### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

The HID class driver sets the <b>Status</b> member of <b>Irp-&gt;IoStatus</b> to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

HID minidrivers that carry out the I/O to the device set the following fields of <b>Irp-&gt;IoStatus</b>:

<ul>
<li>
<b>Information</b> is set to the number of bytes transferred from the device.

</li>
<li>
<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

</li>
</ul>
HID minidrivers that call other drivers with this IRP to carry out the I/O to their device should ensure that the <b>Information</b> field of the status block is correct and not change the contents of the <b>Status</b> field.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539677">HidD_GetPhysicalDescriptor</a>
 

 

