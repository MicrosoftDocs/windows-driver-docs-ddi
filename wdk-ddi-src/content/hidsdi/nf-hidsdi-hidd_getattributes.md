---
UID: NF:hidsdi.HidD_GetAttributes
title: HidD_GetAttributes function (hidsdi.h)
description: The HidD_GetAttributes routine returns the attributes of a specified top-level collection.
old-location: hid\hidd_getattributes.htm
tech.root: hid
ms.assetid: 3b7814a7-828a-40eb-8494-0753d89a95f4
ms.date: 04/30/2018
ms.keywords: HidD_GetAttributes, HidD_GetAttributes routine [Human Input Devices], hid.hidd_getattributes, hidfunc_e4c243d5-b210-409f-b454-68a69c28057c.xml, hidsdi/HidD_GetAttributes
ms.topic: function
f1_keywords:
 - "hidsdi/HidD_GetAttributes"
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
- HidD_GetAttributes
product:
- Windows
targetos: Windows
req.typenames: 
---

# HidD_GetAttributes function


## -description


The <b>HidD_GetAttributes</b> routine returns the attributes of a specified <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection</a>.


## -parameters




### -param HidDeviceObject [in]

Specifies an open handle to a top-level collection.


### -param Attributes [out]

Pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/ns-hidsdi-_hidd_attributes">HIDD_ATTRIBUTES</a> structure that returns the attributes of the collection specified by <i>HidDeviceObject</i>.


## -returns



<b>HidD_GetAttributes </b>returns <b>TRUE</b> if succeeds; otherwise, it returns <b>FALSE</b>.




## -remarks



Only user-mode applications can call <b>HidD_GetAttributes</b>. Kernel-mode drivers can use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_collection_information">IOCTL_HID_GET_COLLECTION_INFORMATION</a>.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/ns-hidsdi-_hidd_attributes">HIDD_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_collection_information">IOCTL_HID_GET_COLLECTION_INFORMATION</a>
 

 

