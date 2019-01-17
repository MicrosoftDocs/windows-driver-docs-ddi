---
UID: NF:hidsdi.HidD_GetPreparsedData
title: HidD_GetPreparsedData function
description: The HidD_GetPreparsedData routine returns a top-level collection's preparsed data.
old-location: hid\hidd_getpreparseddata.htm
tech.root: hid
ms.assetid: e5c550f0-a466-4d0b-ac6f-bcdce600245f
ms.date: 04/30/2018
ms.keywords: HidD_GetPreparsedData, HidD_GetPreparsedData routine [Human Input Devices], hid.hidd_getpreparseddata, hidfunc_e728f2ff-69e2-46d0-8266-7ff011fb8bd5.xml, hidsdi/HidD_GetPreparsedData
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
-	HidD_GetPreparsedData
product:
- Windows
targetos: Windows
req.typenames: 
---

# HidD_GetPreparsedData function


## -description


The <b>HidD_GetPreparsedData</b> routine returns a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection's</a> <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a>.


## -parameters




### -param HidDeviceObject [in]

Specifies an open handle to a top-level collection.


### -param PreparsedData [out]

Pointer to the address of a routine-allocated buffer that contains a collection's preparsed data in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a> structure.


## -returns



<b>HidD_GetPreparsedData</b> returns <b>TRUE</b> if it succeeds; otherwise, it returns <b>FALSE</b>.




## -remarks



Only user-mode applications can call <b>HidD_GetPreparsedData</b>. Kernel-mode drivers can use an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541089">IOCTL_HID_GET_COLLECTION_DESCRIPTOR</a> request.

When an application no longer requires the preparsed data, it should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff538893">HidD_FreePreparsedData</a> to free the preparsed data buffer.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538893">HidD_FreePreparsedData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541089">IOCTL_HID_GET_COLLECTION_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a>
 

 

