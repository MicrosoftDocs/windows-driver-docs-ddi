---
UID: NF:hidsdi.HidD_GetPhysicalDescriptor
title: HidD_GetPhysicalDescriptor function (hidsdi.h)
description: The HidD_GetPhysicalDescriptor routine returns the embedded string of a top-level collection that identifies the collection's physical device.
old-location: hid\hidd_getphysicaldescriptor.htm
tech.root: hid
ms.assetid: 05f853a9-395a-4b2b-b681-0010dd019bbc
ms.date: 04/30/2018
ms.keywords: HidD_GetPhysicalDescriptor, HidD_GetPhysicalDescriptor routine [Human Input Devices], hid.hidd_getphysicaldescriptor, hidfunc_e9532fa2-49f8-41ec-9e23-19416b889b47.xml, hidsdi/HidD_GetPhysicalDescriptor
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hid.dll
api_name:
-	HidD_GetPhysicalDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# HidD_GetPhysicalDescriptor function


## -description


The <b>HidD_GetPhysicalDescriptor</b> routine returns the embedded string of a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> that identifies the collection's physical device.


## -parameters




### -param HidDeviceObject [in]

Specifies an open handle to a top-level collection.


### -param Buffer [out]

Pointer to a caller-allocated buffer that the routine uses to return the requested physical descriptor.


### -param BufferLength [in]

Specifies the length, in bytes, of the buffer at <i>Buffer</i>.


## -returns



<b>HidD_GetPhysicalDescriptor</b> returns <b>TRUE</b> if it succeeds; otherwise, it returns <b>FALSE</b>.




## -remarks



Only user-mode applications can call <b>HidD_GetPhysicalDescriptor</b>. Kernel-mode drivers can use an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541064">IOCTL_GET_PHYSICAL_DESCRIPTOR</a> request.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538927">HidD_GetIndexedString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538959">HidD_GetManufacturerString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539681">HidD_GetProductString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539683">HidD_GetSerialNumberString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541064">IOCTL_GET_PHYSICAL_DESCRIPTOR</a>
 

 

