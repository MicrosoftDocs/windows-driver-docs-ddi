---
UID: NF:hidsdi.HidD_GetManufacturerString
title: HidD_GetManufacturerString function (hidsdi.h)
description: The HidD_GetManufacturerString routine returns a top-level collection's embedded string that identifies the manufacturer.
old-location: hid\hidd_getmanufacturerstring.htm
tech.root: hid
ms.assetid: 21253ed7-d98d-4b97-8d83-01dd18b3c4f9
ms.date: 06/19/2019
keywords: ["HidD_GetManufacturerString function"]
ms.keywords: HidD_GetManufacturerString, HidD_GetManufacturerString routine [Human Input Devices], hid.hidd_getmanufacturerstring, hidfunc_c0e9df6e-0aab-49ac-9a72-196a9b3ceec5.xml, hidsdi/HidD_GetManufacturerString
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
 - HidD_GetManufacturerString
 - hidsdi/HidD_GetManufacturerString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Hid.dll
api_name:
 - HidD_GetManufacturerString
---

# HidD_GetManufacturerString function


## -description

The <b>HidD_GetManufacturerString</b> routine returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection's</a> embedded string that identifies the manufacturer.

## -parameters

### -param HidDeviceObject 

[in]
Specifies an open handle to a top-level collection.

### -param Buffer 

[out]
Pointer to a caller-allocated buffer that the routine uses to return the collection's manufacturer string. The routine returns a NULL-terminated wide character string in a human-readable format.

### -param BufferLength 

[in]
Specifies the length, in bytes, of a caller-allocated buffer provided at <i>Buffer</i>. If the buffer is not large enough to return the entire NULL-terminated embedded string, the routine returns nothing in the buffer.

## -returns

HidD_HidD_GetManufacturerString returns <b>TRUE</b> if it returns the entire NULL-terminated embedded string. Otherwise, the routine returns <b>FALSE</b>. Use [**GetLastError**](https://docs.microsoft.com/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) to get extended error information.

## -remarks

Only user-mode applications can call <b>HidD_GetManufacturerString</b>. Kernel-mode drivers can use an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_manufacturer_string">IOCTL_HID_GET_MANUFACTURER_STRING</a> request.

The maximum possible number of characters in an embedded string is device specific. For USB devices, the maximum string length is 126 wide characters (not including the terminating NULL character).

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getindexedstring">HidD_GetIndexedString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getphysicaldescriptor">HidD_GetPhysicalDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getproductstring">HidD_GetProductString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getserialnumberstring">HidD_GetSerialNumberString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_indexed_string">IOCTL_HID_GET_INDEXED_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_manufacturer_string">IOCTL_HID_GET_MANUFACTURER_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_product_string">IOCTL_HID_GET_PRODUCT_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_serialnumber_string">IOCTL_HID_GET_SERIALNUMBER_STRING</a>

