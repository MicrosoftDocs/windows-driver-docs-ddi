---
UID: NI:hidport.IOCTL_HID_GET_DEVICE_DESCRIPTOR
title: IOCTL_HID_GET_DEVICE_DESCRIPTOR (hidport.h)
description: The IOCTL_HID_GET_DEVICE_DESCRIPTOR request obtains a HIDClass device's HID descriptor.
old-location: hid\ioctl_hid_get_device_descriptor.htm
tech.root: hid
ms.assetid: 89eac71d-c3f9-48b2-9174-26e4ccbe1d6e
ms.date: 04/30/2018
keywords: ["IOCTL_HID_GET_DEVICE_DESCRIPTOR IOCTL"]
ms.keywords: IOCTL_HID_GET_DEVICE_DESCRIPTOR, IOCTL_HID_GET_DEVICE_DESCRIPTOR control, IOCTL_HID_GET_DEVICE_DESCRIPTOR control code [Human Input Devices], hid.ioctl_hid_get_device_descriptor, hidioreq_4994292a-eb5e-4a7e-a1bf-b105836c3b59.xml, hidport/IOCTL_HID_GET_DEVICE_DESCRIPTOR
req.header: hidport.h
req.include-header: Hidport.h
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
 - IOCTL_HID_GET_DEVICE_DESCRIPTOR
 - hidport/IOCTL_HID_GET_DEVICE_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hidport.h
api_name:
 - IOCTL_HID_GET_DEVICE_DESCRIPTOR
---

# IOCTL_HID_GET_DEVICE_DESCRIPTOR IOCTL


## -description

The IOCTL_HID_GET_DEVICE_DESCRIPTOR request obtains a HIDClass device's HID descriptor.

For general information about HIDClass devices, see <a href="/windows-hardware/drivers/hid/hid-collections">HID Collections</a>.

## -ioctlparameters

### -input-buffer

<b>Parameters.DeviceIoControl.OutputBufferLength</b> contains the length of the system-resident buffer provided at <b>Irp->UserBuffer</b>.

### -input-buffer-length

The size of <b>OutputBufferLength</b>.

### -output-buffer

The HID minidriver returns the device descriptor in the user buffer at <b>Irp->UserBuffer</b>.

### -output-buffer-length

The size of the device descriptor.

### -in-out-buffer

### -inout-buffer-length

### -status-block

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

<a href="/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_get_physical_descriptor">IOCTL_GET_PHYSICAL_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/hidport/ni-hidport-ioctl_hid_get_device_attributes">IOCTL_HID_GET_DEVICE_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/ddi/hidport/ni-hidport-ioctl_hid_get_report_descriptor">IOCTL_HID_GET_REPORT_DESCRIPTOR</a>