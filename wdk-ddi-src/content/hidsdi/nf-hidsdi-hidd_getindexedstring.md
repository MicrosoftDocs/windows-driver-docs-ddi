---
UID: NF:hidsdi.HidD_GetIndexedString
title: HidD_GetIndexedString function (hidsdi.h)
description: The HidD_GetIndexedString routine returns a specified embedded string from a top-level collection.
old-location: hid\hidd_getindexedstring.htm
tech.root: hid
ms.assetid: 4d500597-8ac7-41ea-aa2a-6e8d559e0282
ms.date: 06/19/2019
ms.keywords: HidD_GetIndexedString, HidD_GetIndexedString routine [Human Input Devices], hid.hidd_getindexedstring, hidfunc_49698b0b-18d1-41aa-b64c-185307fb2100.xml, hidsdi/HidD_GetIndexedString
ms.topic: function
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Hid.dll
api_name:
- HidD_GetIndexedString
product:
- Windows
targetos: Windows
req.typenames: 
---

# HidD_GetIndexedString function


## -description


The <b>HidD_GetIndexedString</b> routine returns a specified embedded string from a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>.


## -parameters




### -param HidDeviceObject [in]

Specifies an open handle to a top-level collection.


### -param StringIndex [in]

Specifies the device-specific index of an embedded string.


### -param Buffer [out]

Pointer to a caller-allocated buffer that the routine uses to return the embedded string specified by <i>StringIndex</i>. The routine returns a NULL-terminated wide character string in a human-readable format.


### -param BufferLength [in]

Specifies the length, in bytes, of a caller-allocated buffer provided at <i>Buffer</i>. If the buffer is not large enough to return the entire NULL-terminated embedded string, the routine returns nothing in the buffer.


## -returns



<b>HidD_GetIndexedString</b> returns <b>TRUE</b> if it successfully returns the entire NULL-terminated embedded string. Otherwise, the routine returns <b>FALSE</b>. Use [**GetLastError**](https://docs.microsoft.com/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror) to get extended error information.




## -remarks



Only user-mode applications can call <b>HidD_GetIndexedString</b>. Kernel-mode drivers can use an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541109">IOCTL_HID_GET_INDEXED_STRING</a> request.

The maximum possible number of characters in an embedded string is device specific. For USB devices, the maximum string length is 126 wide characters (not including the terminating NULL character). 

The <b>iProduct</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539280">USB_DEVICE_DESCRIPTOR</a> structure for a particular interface is set by the <a href="https://msdn.microsoft.com/80450f25-f887-4580-a5f1-b12724643fad">USB common class generic parent driver</a> based on the following rules:

<ul>
<li>
If the <b>iInterface</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540065">USB_INTERFACE_DESCRIPTOR</a> structure for the interface is nonzero, the <b>iProduct</b> member of the USB_DEVICE_DESCRIPTOR structure for the interface is set to the <b>iInterface</b> member of the USB_INTERFACE_DESCRIPTOR structure.

</li>
<li>
If the interface is grouped by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540054">USB interface association descriptor</a>, and the <b>iFunction</b> member of the interface association descriptor for the interface is nonzero, the <b>iProduct</b> member of the USB_DEVICE_DESCRIPTOR structure for the interface is set to the <b>iFunction</b> member of the interface association descriptor.

</li>
</ul>
For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538959">HidD_GetManufacturerString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539677">HidD_GetPhysicalDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539681">HidD_GetProductString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539683">HidD_GetSerialNumberString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541109">IOCTL_HID_GET_INDEXED_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541134">IOCTL_HID_GET_MANUFACTURER_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541146">IOCTL_HID_GET_PRODUCT_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541160">IOCTL_HID_GET_SERIALNUMBER_STRING</a>
 

 

