---
UID: NI:hidport.IOCTL_HID_ACTIVATE_DEVICE
title: IOCTL_HID_ACTIVATE_DEVICE (hidport.h)
description: The IOCTL_HID_ACTIVATE_DEVICE request activates a HIDClass device, which makes it ready for I/O operations.
old-location: hid\ioctl_hid_activate_device.htm
tech.root: hid
ms.assetid: 5d2f218c-a9a5-4149-8fde-898171dfc9a7
ms.date: 04/30/2018
ms.keywords: IOCTL_HID_ACTIVATE_DEVICE, IOCTL_HID_ACTIVATE_DEVICE control, IOCTL_HID_ACTIVATE_DEVICE control code [Human Input Devices], hid.ioctl_hid_activate_device, hidioreq_031bb843-02fe-4859-acf2-4bcbfaaea657.xml, hidport/IOCTL_HID_ACTIVATE_DEVICE
ms.topic: ioctl
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
- IOCTL_HID_ACTIVATE_DEVICE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_HID_ACTIVATE_DEVICE IOCTL


## -description


The IOCTL_HID_ACTIVATE_DEVICE request activates a HIDClass device, which makes it ready for I/O operations.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 


## -ioctlparameters




### -input-buffer

<b>Parameters.DeviceIoControl.Type3InputBuffer</b> contains a collection identifier, as a ULONG value, of the collection to activate.


### -input-buffer-length

The length of a ULONG value.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block


       HID minidrivers that carry out the I/O to the device set the following fields of <b>Irp->IoStatus</b>:

<ul>
<li>
<b>Information</b> is set to zero.

</li>
<li>
<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

</li>
</ul>
Minidrivers that call other drivers with this IRP to carry out the I/O to their device should ensure that the <b>Information</b> field of the status block is zero and not change the contents of the <b>Status</b> field.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541075">IOCTL_HID_DEACTIVATE_DEVICE</a>
 

 

