---
UID: NF:hidsdi.HidD_GetAttributes
title: HidD_GetAttributes function
author: windows-driver-content
description: The HidD_GetAttributes routine returns the attributes of a specified top-level collection.
old-location: hid\hidd_getattributes.htm
old-project: hid
ms.assetid: 3b7814a7-828a-40eb-8494-0753d89a95f4
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: HidD_GetAttributes, HidD_GetAttributes routine [Human Input Devices], hid.hidd_getattributes, hidfunc_e4c243d5-b210-409f-b454-68a69c28057c.xml, hidsdi/HidD_GetAttributes
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	HidD_GetAttributes
product: Windows
targetos: Windows
req.typenames: HID_MINIDRIVER_REGISTRATION, *PHID_MINIDRIVER_REGISTRATION
---

# HidD_GetAttributes function


## -description


The <b>HidD_GetAttributes</b> routine returns the attributes of a specified <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>.


## -parameters




### -param HidDeviceObject [in]

Specifies an open handle to a top-level collection.


### -param Attributes [out]

Pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff538868">HIDD_ATTRIBUTES</a> structure that returns the attributes of the collection specified by <i>HidDeviceObject</i>.


## -returns



<b>HidD_GetAttributes </b>returns <b>TRUE</b> if succeeds; otherwise, it returns <b>FALSE</b>.




## -remarks



Only user-mode applications can call <b>HidD_GetAttributes</b>. Kernel-mode drivers can use <a href="https://msdn.microsoft.com/library/windows/hardware/ff541092">IOCTL_HID_GET_COLLECTION_INFORMATION</a>.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538868">HIDD_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541092">IOCTL_HID_GET_COLLECTION_INFORMATION</a>
 

 

