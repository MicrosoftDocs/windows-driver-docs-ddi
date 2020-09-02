---
UID: NI:hidport.IOCTL_HID_GET_STRING
title: IOCTL_HID_GET_STRING (hidport.h)
description: The IOCTL_HID_GET_STRING request obtains a manufacturer ID, product ID, or serial number for a top-level collection. The retrieved string is a NULL-terminated wide character string in a human-readable format.
old-location: hid\ioctl_hid_get_string.htm
tech.root: hid
ms.assetid: 0812f27f-f38c-487d-9e92-98e16ddde21c
ms.date: 04/30/2018
keywords: ["IOCTL_HID_GET_STRING IOCTL"]
ms.keywords: IOCTL_HID_GET_STRING, IOCTL_HID_GET_STRING control, IOCTL_HID_GET_STRING control code [Human Input Devices], hid.ioctl_hid_get_string, hidioreq_987af494-0ac9-4b86-ab66-63dad179cec5.xml, hidport/IOCTL_HID_GET_STRING
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
 - IOCTL_HID_GET_STRING
 - hidport/IOCTL_HID_GET_STRING
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hidport.h
api_name:
 - IOCTL_HID_GET_STRING
---

# IOCTL_HID_GET_STRING IOCTL


## -description

The IOCTL_HID_GET_STRING request obtains a manufacturer ID, product ID, or serial number for a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection</a>. The retrieved string is a NULL-terminated wide character string in a human-readable format.

For general information about HIDClass devices, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>.

## -ioctlparameters

### -input-buffer

IOCTL_HID_GET_STRING makes use of two input buffers.

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the locked-down output buffer at <b>Irp->UserBuffer</b>. If the output buffer is not large enough to hold the entire NULL-terminated embedded string, the request returns nothing in the output buffer. The maximum possible number of characters in an embedded string is device specific. For USB devices, the maximum string length is 126 wide characters (not including the terminating NULL character). 

<b>Parameters.DeviceIoControl.Type3InputBuffer</b> in the I/O stack location of the IRP contains a composite value. The two most significant bytes contain the language ID of the string to be retrieved. The two least significant bytes contain one of the following three constant values: 

<ul>
<li>
HID_STRING_ID_IMANUFACTURER

</li>
<li>
HID_STRING_ID_IPRODUCT

</li>
<li>
HID_STRING_ID_ISERIALNUMBER

</li>
</ul>
The HID minidriver determines which of these three constants is present in the lower two bytes of the input buffer, then it must retrieve the corresponding string index from the device descriptor. Device descriptor information is stored in the device extension of a top-level collection associated with the device.

It is important not to confuse these three constants with the actual string indices of the IDs. These constants represent the offsets in the device descriptor where the corresponding string indices can be found.

For example, HID_STRING_ID_IMANUFACTURER indicates the location in the device descriptor where the index for the manufacturer ID is found. This index, in turn, serves as an offset into the string descriptor where the human-readable form of the manufacturer ID is located.

### -input-buffer-length

The size of the <b>OutputBufferLength</b> and the size of the <b>Type3InputBuffer</b>.

### -output-buffer

The HID minidriver fills the buffer at <b>Irp->UserBuffer</b> with the requested string (a NULL-terminated wide character string).

### -output-buffer-length

The size of the <b>UserBuffer</b>.

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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getindexedstring">HidD_GetIndexedString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getmanufacturerstring">HidD_GetManufacturerString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getproductstring">HidD_GetProductString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getserialnumberstring">HidD_GetSerialNumberString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_indexed_string">IOCTL_HID_GET_INDEXED_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_manufacturer_string">IOCTL_HID_GET_MANUFACTURER_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_product_string">IOCTL_HID_GET_PRODUCT_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_serialnumber_string">IOCTL_HID_GET_SERIALNUMBER_STRING</a>

