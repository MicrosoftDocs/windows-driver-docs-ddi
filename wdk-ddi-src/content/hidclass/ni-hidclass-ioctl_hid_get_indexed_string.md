---
UID: NI:hidclass.IOCTL_HID_GET_INDEXED_STRING
title: IOCTL_HID_GET_INDEXED_STRING (hidclass.h)
description: The IOCTL_HID_GET_INDEXED_STRING request obtains a specified embedded string from a top-level collection.
old-location: hid\ioctl_hid_get_indexed_string2.htm
tech.root: hid
ms.date: 04/30/2018
keywords: ["IOCTL_HID_GET_INDEXED_STRING IOCTL"]
ms.keywords: IOCTL_HID_GET_INDEXED_STRING, IOCTL_HID_GET_INDEXED_STRING control, IOCTL_HID_GET_INDEXED_STRING control code [Human Input Devices], hid.ioctl_hid_get_indexed_string2, hidclass/IOCTL_HID_GET_INDEXED_STRING, hidioreq_ab829578-5003-4082-9c70-d81d59fb5015.xml
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
 - IOCTL_HID_GET_INDEXED_STRING
 - hidclass/IOCTL_HID_GET_INDEXED_STRING
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hidclass.h
api_name:
 - IOCTL_HID_GET_INDEXED_STRING
---

# IOCTL_HID_GET_INDEXED_STRING IOCTL

## -description

The IOCTL_HID_GET_INDEXED_STRING request obtains a specified embedded string from a [top-level collection](/windows-hardware/drivers/hid/top-level-collections). The retrieved string is a NULL-terminated wide character string in a human-readable format.

For general information about HIDClass devices see [HID Collections](/windows-hardware/drivers/hid/hid-collections).

## -ioctlparameters

### -input-buffer

**Parameters.DeviceIoControl.InputBufferLength** in the I/O stack location of the IRP indicates the size in bytes of the input buffer at the location pointed to by **Irp->AssociatedIrp.SystemBuffer**.

**Parameters.DeviceIoControl.OutputBufferLength** in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer. If the output buffer is not large enough to hold the entire NULL-terminated embedded string, the request returns nothing in the output buffer.  

**Minidriver handling**: IOCTL_HID_GET_INDEXED_STRING uses two input buffers.

**Parameters.DeviceIoControl.OutputBufferLength** in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer at the location pointed to by **Irp->MdlAddress**. If the output buffer is not large enough to hold the entire NULL-terminated embedded string, the request returns nothing in the output buffer. The maximum possible number of characters in an embedded string is device specific. For USB devices, the maximum string length is 126 wide characters (not including the terminating NULL character).

**Parameters.DeviceIoControl.Type3InputBuffer** contains an INT value that describes the string to be retrieved. The most significant two bytes of the INT value contain the language ID (for example, a value of 1033 indicates English). The least significant two bytes of the INT value contain the string index.

### -input-buffer-length

**Parameters.DeviceIoControl.InputBufferLength** must be >= **sizeof**(ULONG) and it should contain the index of the string to be retrieved.

For **Parameters.DeviceIoControl.OutputBufferLength**, the maximum possible number of characters in an embedded string is device specific. For USB devices, the maximum string length is 126 wide characters (not including the terminating NULL character).

### -output-buffer

**Irp->MdlAddress** points to a buffer to receive the retrieved string (a NULL-terminated wide character string). 

**Minidriver handling**: **Irp->MdlAddress** points to a buffer to receive the retrieved string (a NULL-terminated wide character string). Note that unlike most device control IRPs for HID minidrivers, this IRP does not use METHOD_NEITHER buffering. In particular, it must be distinguished from IOCTL_HID_GET_STRING whose output buffer is identified by **Irp->UserBuffer**.

### -output-buffer-length

The length of the retrieved string (a NULL-terminated wide character string). The supplied buffer must be <= 4093 bytes (2^12 – 3).

### -in-out-buffer

### -inout-buffer-length

### -status-block

The HID class driver sets the following fields of **Irp->IoStatus**:

- **Information** is set to the number of bytes transferred from the device.

- **Status** is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

## -see-also

[HidD_GetIndexedString](/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getindexedstring)

[HidD_GetManufacturerString](/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getmanufacturerstring)

[HidD_GetPhysicalDescriptor](/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getphysicaldescriptor)

[HidD_GetProductString](/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getproductstring)

[HidD_GetSerialNumberString](/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getserialnumberstring)

[IOCTL_HID_GET_MANUFACTURER_STRING](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_manufacturer_string)

[IOCTL_HID_GET_PRODUCT_STRING](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_product_string)

[IOCTL_HID_GET_SERIALNUMBER_STRING](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_serialnumber_string)
