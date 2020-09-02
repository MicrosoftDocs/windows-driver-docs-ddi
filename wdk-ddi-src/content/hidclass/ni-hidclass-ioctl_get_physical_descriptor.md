---
UID: NI:hidclass.IOCTL_GET_PHYSICAL_DESCRIPTOR
title: IOCTL_GET_PHYSICAL_DESCRIPTOR (hidclass.h)
description: The IOCTL_GET_PHYSICAL_DESCRIPTOR request obtains the physical descriptor of a top-level collection. For a minidriver, this descriptor is the descriptor of the HIDClass device.
old-location: hid\ioctl_get_physical_descriptor.htm
tech.root: hid
ms.assetid: cf15dd7f-4568-40c7-b2e4-7cec8239df0b
ms.date: 04/30/2018
keywords: ["IOCTL_GET_PHYSICAL_DESCRIPTOR IOCTL"]
ms.keywords: IOCTL_GET_PHYSICAL_DESCRIPTOR, IOCTL_GET_PHYSICAL_DESCRIPTOR control, IOCTL_GET_PHYSICAL_DESCRIPTOR control code [Human Input Devices], hid.ioctl_get_physical_descriptor, hidclass/IOCTL_GET_PHYSICAL_DESCRIPTOR, hidioreq_3a61c6d2-a97a-47d6-86b1-317e22775271.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_GET_PHYSICAL_DESCRIPTOR
 - hidclass/IOCTL_GET_PHYSICAL_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hidclass.h
api_name:
 - IOCTL_GET_PHYSICAL_DESCRIPTOR
---

# IOCTL_GET_PHYSICAL_DESCRIPTOR IOCTL


## -description

The IOCTL_GET_PHYSICAL_DESCRIPTOR request obtains the physical descriptor of a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection</a>. For a minidriver, this descriptor is the descriptor of the HIDClass device.

For general information about HIDClass devices, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>.

## -ioctlparameters

### -input-buffer

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer.

### -input-buffer-length

### -output-buffer

<b>Irp->MdlAddress</b> must point to the buffer that will receive the physical descriptor. 

The HID minidriver copies the physical descriptor into the user buffer at <b>Irp->UserBuffer</b>.

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

The HID class driver sets the <b>Status</b> member of <b>Irp->IoStatus</b> to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

HID minidrivers that carry out the I/O to the device set the following fields of <b>Irp->IoStatus</b>:

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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getphysicaldescriptor">HidD_GetPhysicalDescriptor</a>

