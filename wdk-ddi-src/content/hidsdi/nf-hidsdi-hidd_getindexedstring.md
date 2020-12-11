---
UID: NF:hidsdi.HidD_GetIndexedString
title: HidD_GetIndexedString function (hidsdi.h)
description: The HidD_GetIndexedString routine returns a specified embedded string from a top-level collection.
old-location: hid\hidd_getindexedstring.htm
tech.root: hid
ms.assetid: 4d500597-8ac7-41ea-aa2a-6e8d559e0282
ms.date: 06/19/2019
keywords: ["HidD_GetIndexedString function"]
ms.keywords: HidD_GetIndexedString, HidD_GetIndexedString routine [Human Input Devices], hid.hidd_getindexedstring, hidfunc_49698b0b-18d1-41aa-b64c-185307fb2100.xml, hidsdi/HidD_GetIndexedString
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
 - HidD_GetIndexedString
 - hidsdi/HidD_GetIndexedString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Hid.dll
api_name:
 - HidD_GetIndexedString
---

# HidD_GetIndexedString function

## -description

The **HidD_GetIndexedString** routine returns a specified embedded string from a [top-level collection](/windows-hardware/drivers/hid/top-level-collections).

## -parameters

### -param HidDeviceObject

[in]
Specifies an open handle to a top-level collection.

### -param StringIndex

[in]
Specifies the device-specific index of an embedded string.

### -param Buffer

[out]
Pointer to a caller-allocated buffer that the routine uses to return the embedded string specified by *StringIndex*. The routine returns a NULL-terminated wide character string in a human-readable format.

### -param BufferLength

[in]
Specifies the length, in bytes, of a caller-allocated buffer provided at *Buffer*. If the buffer is not large enough to return the entire NULL-terminated embedded string, the routine returns nothing in the buffer. The supplied buffer must be <= 4093 bytes (2^12 – 3).

## -returns

**HidD_GetIndexedString** returns **TRUE** if it successfully returns the entire NULL-terminated embedded string. Otherwise, the routine returns **FALSE**. Use [**GetLastError**](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) to get extended error information.

## -remarks

Only user-mode applications can call **HidD_GetIndexedString**. Kernel-mode drivers can use an [IOCTL_HID_GET_INDEXED_STRING](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_indexed_string) request.

The maximum possible number of characters in an embedded string is device specific. For USB devices, the maximum string length is 126 wide characters (not including the terminating NULL character).

The **iProduct** member of a [USB_DEVICE_DESCRIPTOR](/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_device_descriptor) structure for a particular interface is set by the [USB common class generic parent driver](/windows-hardware/drivers/ddi/index) based on the following rules:

- If the **iInterface** member of the [USB_INTERFACE_DESCRIPTOR](/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_interface_descriptor) structure for the interface is nonzero, the **iProduct** member of the USB_DEVICE_DESCRIPTOR structure for the interface is set to the **iInterface** member of the USB_INTERFACE_DESCRIPTOR structure.

- If the interface is grouped by a [USB interface association descriptor](/windows-hardware/drivers/ddi/index) and the **iFunction** member of the interface association descriptor for the interface is nonzero, the **iProduct** member of the USB_DEVICE_DESCRIPTOR structure for the interface is set to the **iFunction** member of the interface association descriptor.

If the supplied buffer is not <= 4093 bytes (2^12 – 3) the call may fail (depending on the underlying protocol, HID/Bluetooth/SPI) with error code ERROR_GEN_FAILURE (0x0000001f)

For more information see [HID Collections](/windows-hardware/drivers/hid/hid-collections).

## -see-also

[HidD_GetManufacturerString](/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getmanufacturerstring)

[HidD_GetPhysicalDescriptor](/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getphysicaldescriptor)

[HidD_GetProductString](/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getproductstring)

[HidD_GetSerialNumberString](/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getserialnumberstring)

[IOCTL_HID_GET_INDEXED_STRING](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_indexed_string)

[IOCTL_HID_GET_MANUFACTURER_STRING](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_manufacturer_string)

[IOCTL_HID_GET_PRODUCT_STRING](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_product_string)

[IOCTL_HID_GET_SERIALNUMBER_STRING](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_serialnumber_string)
