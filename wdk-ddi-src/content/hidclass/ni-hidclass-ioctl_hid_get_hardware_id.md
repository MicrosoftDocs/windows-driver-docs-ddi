---
UID: NI:hidclass.IOCTL_HID_GET_HARDWARE_ID
title: IOCTL_HID_GET_HARDWARE_ID (hidclass.h)
description: The IOCTL_HID_GET_HARDWARE_ID request obtains the Plug and Play hardware ID of a top-level collection.
old-location: hid\ioctl_hid_get_hardware_id.htm
tech.root: hid
ms.assetid: 33da3d63-0909-45fe-9a3b-d268b352231c
ms.date: 04/30/2018
ms.keywords: IOCTL_HID_GET_HARDWARE_ID, IOCTL_HID_GET_HARDWARE_ID control, IOCTL_HID_GET_HARDWARE_ID control code [Human Input Devices], hid.ioctl_hid_get_hardware_id, hidclass/IOCTL_HID_GET_HARDWARE_ID, hidioreq_e5eb1673-bf55-451b-b8de-f8d735aa54eb.xml
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
- IOCTL_HID_GET_HARDWARE_ID
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_HID_GET_HARDWARE_ID IOCTL


## -description


The IOCTL_HID_GET_HARDWARE_ID request obtains the Plug and Play hardware ID of a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection</a>. 

For general information about HIDClass devices, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>. 


## -ioctlparameters




### -input-buffer

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer. 


### -input-buffer-length

The length of the buffer.


### -output-buffer

<b>Irp->MdlAddress</b> points to a buffer to receive the number of device input buffers. 


### -output-buffer-length

The length of the buffer.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The HID class driver sets the following fields of <b>Irp->IoStatus</b>:

<ul>
<li>
<b>Information</b> is set to the number of bytes of registry information retrieved when the IOCTL succeeds. 

</li>
<li>
<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

</li>
</ul>

## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidsdi/nf-hidsdi-hidd_getindexedstring">HidD_GetIndexedString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidsdi/nf-hidsdi-hidd_getmanufacturerstring">HidD_GetManufacturerString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidsdi/nf-hidsdi-hidd_getproductstring">HidD_GetProductString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidsdi/nf-hidsdi-hidd_getserialnumberstring">HidD_GetSerialNumberString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidclass/ni-hidclass-ioctl_hid_get_indexed_string">IOCTL_HID_GET_INDEXED_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidclass/ni-hidclass-ioctl_hid_get_manufacturer_string">IOCTL_HID_GET_MANUFACTURER_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidclass/ni-hidclass-ioctl_hid_get_product_string">IOCTL_HID_GET_PRODUCT_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidclass/ni-hidclass-ioctl_hid_get_serialnumber_string">IOCTL_HID_GET_SERIALNUMBER_STRING</a>
 

 

