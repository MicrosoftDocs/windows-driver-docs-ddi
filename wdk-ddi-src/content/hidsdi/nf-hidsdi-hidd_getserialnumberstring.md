---
UID: NF:hidsdi.HidD_GetSerialNumberString
title: HidD_GetSerialNumberString function (hidsdi.h)
description: The HidD_GetSerialNumberString routine returns the embedded string of a top-level collection that identifies the serial number of the collection's physical device.
old-location: hid\hidd_getserialnumberstring.htm
tech.root: hid
ms.assetid: 807f1432-1b2f-45fc-899c-b2920ea79f7a
ms.date: 06/19/2019
keywords: ["HidD_GetSerialNumberString function"]
ms.keywords: HidD_GetSerialNumberString, HidD_GetSerialNumberString routine [Human Input Devices], hid.hidd_getserialnumberstring, hidfunc_b01ce302-052c-43f1-9b8f-6421ebb66954.xml, hidsdi/HidD_GetSerialNumberString
req.header: hidsdi.h
req.include-header: Hidsdi.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
req.lib: Hid.lib
req.dll: Hid.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - HidD_GetSerialNumberString
 - hidsdi/HidD_GetSerialNumberString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Hid.dll
api_name:
 - HidD_GetSerialNumberString
---

# HidD_GetSerialNumberString function

## -description

The **HidD_GetSerialNumberString** routine returns the embedded string of a [top-level collection](/windows-hardware/drivers/hid/top-level-collections) that identifies the serial number of the collection's physical device.

## -parameters

### -param HidDeviceObject [in]


Specifies an open handle to a top-level collection.

### -param Buffer [out]


Pointer to a caller-allocated buffer that the routine uses to return the requested serial number string. The routine returns a NULL-terminated wide character string.

### -param BufferLength [in]


Specifies the length, in bytes, of a caller-allocated buffer provided at *Buffer*. If the buffer is not large enough to return the entire NULL-terminated embedded string, the routine returns nothing in the buffer. The supplied buffer must be <= 4093 bytes (2^12 – 3).

## -returns

**HidD_GetSerialNumberString** returns **TRUE** if it successfully returns the entire NULL-terminated embedded string. Otherwise, the routine returns **FALSE**. Use [**GetLastError**](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) to get extended error information.

## -remarks

Only user-mode applications can call **HidD_GetSerialNumberString**. Kernel-mode drivers can use [IOCTL_HID_GET_SERIALNUMBER_STRING](../hidclass/ni-hidclass-ioctl_hid_get_serialnumber_string.md).

The maximum possible number of characters in an embedded string is device specific. For USB devices, the maximum string length is 126 wide characters (not including the terminating NULL character).

If the supplied buffer is not <= 4093 bytes (2^12 – 3), the call may fail (depending on the underlying protocol, HID/Bluetooth/SPI) with error code ERROR_GEN_FAILURE (0x0000001f)

For more information see [HID Collections](/windows-hardware/drivers/hid/hid-collections).

## -see-also

[HidD_GetManufacturerString](./nf-hidsdi-hidd_getmanufacturerstring.md)

[HidD_GetPhysicalDescriptor](./nf-hidsdi-hidd_getphysicaldescriptor.md)

[HidD_GetProductString](./nf-hidsdi-hidd_getproductstring.md)

[IOCTL_HID_GET_INDEXED_STRING](../hidclass/ni-hidclass-ioctl_hid_get_indexed_string.md)

[IOCTL_HID_GET_MANUFACTURER_STRING](../hidclass/ni-hidclass-ioctl_hid_get_manufacturer_string.md)

[IOCTL_HID_GET_PRODUCT_STRING](../hidclass/ni-hidclass-ioctl_hid_get_product_string.md)

[IOCTL_HID_GET_SERIALNUMBER_STRING](../hidclass/ni-hidclass-ioctl_hid_get_serialnumber_string.md)
