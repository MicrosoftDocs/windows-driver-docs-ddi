---
UID: NI:hidport.IOCTL_HID_GET_DEVICE_ATTRIBUTES
title: IOCTL_HID_GET_DEVICE_ATTRIBUTES
author: windows-driver-content
description: The IOCTL_HID_GET_DEVICE_ATTRIBUTES request obtains a HIDClass device's attributes in a HID_DEVICE_ATTRIBUTES structure.
old-location: hid\ioctl_hid_get_device_attributes.htm
old-project: hid
ms.assetid: ee68c045-e99a-471d-ae22-396673d68168
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_HID_GET_DEVICE_ATTRIBUTES, IOCTL_HID_GET_DEVICE_ATTRIBUTES control code [Human Input Devices], hid.ioctl_hid_get_device_attributes, hidioreq_417c2e10-9ca8-4a9f-8a30-1ff401b65b13.xml, hidport/IOCTL_HID_GET_DEVICE_ATTRIBUTES
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hidport.h
api_name:
-	IOCTL_HID_GET_DEVICE_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: USAGE_AND_PAGE, *PUSAGE_AND_PAGE
---

# IOCTL_HID_GET_DEVICE_ATTRIBUTES IOCTL


## -description


The IOCTL_HID_GET_DEVICE_ATTRIBUTES request obtains a HIDClass device's attributes in a <a href="..\hidport\ns-hidport-_hid_device_attributes.md">HID_DEVICE_ATTRIBUTES</a> structure.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 


## -ioctlparameters




### -input-buffer

<b>Parameters.DeviceIoControl.OutputBufferLength</b> contains the length, in bytes, of the HID class driver's buffer located at <b>Irp-&gt;UserBuffer</b>. 


### -input-buffer-length

The size, in bytes, of the buffer must be greater than or equal to the size, in bytes, of a HID_DEVICE_ATTRIBUTES structure.


### -output-buffer

The HID minidriver returns the device attributes in a HID_DEVICE_ATTRIBUTES structure at <b>Irp-&gt;UserBuffer</b>.


### -output-buffer-length

The size of a HID_DEVICE_ATTRIBUTES structure.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The HID minidriver sets the following fields of <b>Irp-&gt;IoStatus</b>:

<ul>
<li>
<b>Information</b> is set to the number of bytes transferred from the device.

</li>
<li>
<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

</li>
</ul>

## -see-also

<a href="..\hidport\ni-hidport-ioctl_hid_get_device_descriptor.md">IOCTL_HID_GET_DEVICE_DESCRIPTOR</a>



<a href="..\hidport\ns-hidport-_hid_device_attributes.md">HID_DEVICE_ATTRIBUTES</a>



 

 


