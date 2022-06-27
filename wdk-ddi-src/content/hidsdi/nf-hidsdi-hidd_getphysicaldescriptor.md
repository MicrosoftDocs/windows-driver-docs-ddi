---
UID: NF:hidsdi.HidD_GetPhysicalDescriptor
title: HidD_GetPhysicalDescriptor function (hidsdi.h)
description: The HidD_GetPhysicalDescriptor routine returns the embedded string of a top-level collection that identifies the collection's physical device.
old-location: hid\hidd_getphysicaldescriptor.htm
tech.root: hid
ms.date: 06/19/2019
keywords: ["HidD_GetPhysicalDescriptor function"]
ms.keywords: HidD_GetPhysicalDescriptor, HidD_GetPhysicalDescriptor routine [Human Input Devices], hid.hidd_getphysicaldescriptor, hidfunc_e9532fa2-49f8-41ec-9e23-19416b889b47.xml, hidsdi/HidD_GetPhysicalDescriptor
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
 - HidD_GetPhysicalDescriptor
 - hidsdi/HidD_GetPhysicalDescriptor
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Hid.dll
api_name:
 - HidD_GetPhysicalDescriptor
---

# HidD_GetPhysicalDescriptor function

## -description

The <b>HidD_GetPhysicalDescriptor</b> routine returns the _Physical Descriptor_ of a <a href="/windows-hardware/drivers/hid/top-level-collections">top-level collection</a> that identifies the collection's physical device. 

_Physical Descriptor_ is used to indicate what physical part of the human body is used to activate the controls on a device. For example, a _Physical Descriptor_ might indicate that the right hand thumb is used to activate button 5.

Note that _Physical Descriptors_ are entirely optional. They add complexity and offer very little in return for most devices. However, some devices, particularly those with a large number of identical controls (for example, buttons) will find that _Physical Descriptors_ help different applications assign functionality to these controls in a more consistent manner. See <a href="https://www.usb.org/hid">HID specification</a> for more info.

## -parameters

### -param HidDeviceObject [in]

Specifies an open handle to a top-level collection.

### -param Buffer [out]

Pointer to a caller-allocated buffer that the routine uses to return the requested physical descriptor.

### -param BufferLength [in]

Specifies the length, in bytes, of the buffer at <i>Buffer</i>.

## -returns

<b>HidD_GetPhysicalDescriptor</b> returns <b>TRUE</b> if it succeeds; otherwise, it returns <b>FALSE</b>. Use [**GetLastError**](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) to get extended error information.

## -remarks

Only user-mode applications can call <b>HidD_GetPhysicalDescriptor</b>. Kernel-mode drivers can use an <a href="/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_get_physical_descriptor">IOCTL_GET_PHYSICAL_DESCRIPTOR</a> request.

For more information, see <a href="/windows-hardware/drivers/hid/hid-collections">HID Collections</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getindexedstring">HidD_GetIndexedString</a>

<a href="/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getmanufacturerstring">HidD_GetManufacturerString</a>

<a href="/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getproductstring">HidD_GetProductString</a>

<a href="/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getserialnumberstring">HidD_GetSerialNumberString</a>

<a href="/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_get_physical_descriptor">IOCTL_GET_PHYSICAL_DESCRIPTOR</a>
