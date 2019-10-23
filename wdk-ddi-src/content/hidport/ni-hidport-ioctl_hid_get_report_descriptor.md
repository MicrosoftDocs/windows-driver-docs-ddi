---
UID: NI:hidport.IOCTL_HID_GET_REPORT_DESCRIPTOR
title: IOCTL_HID_GET_REPORT_DESCRIPTOR (hidport.h)
description: The IOCTL_HID_GET_REPORT_DESCRIPTOR request obtains the report descriptor for a HIDClass device.
old-location: hid\ioctl_hid_get_report_descriptor.htm
tech.root: hid
ms.assetid: 7f0e6295-9c96-4167-8414-6f7b7b171f37
ms.date: 04/30/2018
ms.keywords: IOCTL_HID_GET_REPORT_DESCRIPTOR, IOCTL_HID_GET_REPORT_DESCRIPTOR control, IOCTL_HID_GET_REPORT_DESCRIPTOR control code [Human Input Devices], hid.ioctl_hid_get_report_descriptor, hidioreq_01b638bd-f2d5-4acc-8527-9fd98bde8144.xml, hidport/IOCTL_HID_GET_REPORT_DESCRIPTOR
ms.topic: ioctl
f1_keywords:
 - "hidport/IOCTL_HID_GET_REPORT_DESCRIPTOR"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- hidport.h
api_name:
- IOCTL_HID_GET_REPORT_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_HID_GET_REPORT_DESCRIPTOR IOCTL


## -description


The IOCTL_HID_GET_REPORT_DESCRIPTOR request obtains the report descriptor for a HIDClass device.

For general information about HIDClass devices, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>. 


## -ioctlparameters




### -input-buffer

<b>Parameters.DeviceIoControl.OutputBufferLength</b> specifies the length, in bytes, of the locked-down buffer at <b>Irp->UserBuffer</b>.


### -input-buffer-length

The size of <b>OutputBufferLength</b>.


### -output-buffer

The HID minidriver fills the buffer at <b>Irp->UserBuffer</b> with the report descriptor.


### -output-buffer-length

The size of the report descriptor.


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
HID minidrivers that call other drivers with this IOCTL to carry out the I/O to their device, should ensure that the <b>Information</b> field of the status block is correct and not change the contents of the <b>Status</b> field.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_get_physical_descriptor">IOCTL_GET_PHYSICAL_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/previous-versions/hh439622(v=vs.85)">IOCTL_HID_GET_DEVICE_DESCRIPTOR</a>
 

 

