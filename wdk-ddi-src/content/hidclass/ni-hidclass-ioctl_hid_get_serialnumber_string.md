---
UID: NI:hidclass.IOCTL_HID_GET_SERIALNUMBER_STRING
title: IOCTL_HID_GET_SERIALNUMBER_STRING (hidclass.h)
description: The IOCTL_HID_GET_SERIALNUMBER_STRING request obtains a top-level collection's embedded string that identifies the device's serial number.
old-location: hid\ioctl_hid_get_serialnumber_string.htm
tech.root: hid
ms.date: 04/30/2018
keywords: ["IOCTL_HID_GET_SERIALNUMBER_STRING IOCTL"]
ms.keywords: IOCTL_HID_GET_SERIALNUMBER_STRING, IOCTL_HID_GET_SERIALNUMBER_STRING control, IOCTL_HID_GET_SERIALNUMBER_STRING control code [Human Input Devices], hid.ioctl_hid_get_serialnumber_string, hidclass/IOCTL_HID_GET_SERIALNUMBER_STRING, hidioreq_6f0fd737-3834-4f3e-be8d-4027b6525c87.xml
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
 - IOCTL_HID_GET_SERIALNUMBER_STRING
 - hidclass/IOCTL_HID_GET_SERIALNUMBER_STRING
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hidclass.h
api_name:
 - IOCTL_HID_GET_SERIALNUMBER_STRING
---

# IOCTL_HID_GET_SERIALNUMBER_STRING IOCTL


## -description

The IOCTL_HID_GET_SERIALNUMBER_STRING request obtains a <a href="/windows-hardware/drivers/hid/top-level-collections">top-level collection's</a> embedded string that identifies the device's serial number. The retrieved string is a NULL-terminated wide character string in a human-readable format.

For general information about HIDClass devices, see <a href="/windows-hardware/drivers/hid/hid-collections">HID Collections</a>.

## -ioctlparameters

### -input-buffer

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer. If the output buffer is not large enough to hold the entire NULL-terminated embedded string, the request returns nothing in the output buffer.

### -input-buffer-length

The maximum possible number of characters in an embedded string is device specific. For USB devices, the maximum string length is 126 wide characters (not including the terminating NULL character).

### -output-buffer

<b>Irp->MdlAddress</b> points to a buffer to receive the serial number string (a NULL-terminated wide character string).

### -output-buffer-length

The length of a NULL-terminated wide character string.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The HID class driver sets the following fields of <b>Irp->IoStatus</b>:

<ul>
<li>
<b>Information</b> is set to the number of bytes transferred from the device.

</li>
<li>
<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

</li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getindexedstring">HidD_GetIndexedString</a>



<a href="/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getmanufacturerstring">HidD_GetManufacturerString</a>



<a href="/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getphysicaldescriptor">HidD_GetPhysicalDescriptor</a>



<a href="/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getproductstring">HidD_GetProductString</a>



<a href="/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getserialnumberstring">HidD_GetSerialNumberString</a>



<a href="/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_indexed_string">IOCTL_HID_GET_INDEXED_STRING</a>



<a href="/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_manufacturer_string">IOCTL_HID_GET_MANUFACTURER_STRING</a>



<a href="/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_product_string">IOCTL_HID_GET_PRODUCT_STRING</a>
