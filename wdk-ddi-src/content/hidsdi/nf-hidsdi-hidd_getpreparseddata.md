---
UID: NF:hidsdi.HidD_GetPreparsedData
title: HidD_GetPreparsedData function (hidsdi.h)
description: The HidD_GetPreparsedData routine returns a top-level collection's preparsed data.
old-location: hid\hidd_getpreparseddata.htm
tech.root: hid
ms.assetid: e5c550f0-a466-4d0b-ac6f-bcdce600245f
ms.date: 06/19/2019
keywords: ["HidD_GetPreparsedData function"]
ms.keywords: HidD_GetPreparsedData, HidD_GetPreparsedData routine [Human Input Devices], hid.hidd_getpreparseddata, hidfunc_e728f2ff-69e2-46d0-8266-7ff011fb8bd5.xml, hidsdi/HidD_GetPreparsedData
f1_keywords:
 - "hidsdi/HidD_GetPreparsedData"
 - "HidD_GetPreparsedData"
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
- HidD_GetPreparsedData
targetos: Windows
req.typenames: 
---

# HidD_GetPreparsedData function


## -description


The **HidD_GetPreparsedData** routine returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection's</a> <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/preparsed-data">preparsed data</a>.


## -parameters




### -param HidDeviceObject 
[in]
Specifies an open handle to a top-level collection.


### -param PreparsedData 
[out]
Pointer to the address of a routine-allocated buffer that contains a collection's preparsed data in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getpreparseddata">_HIDP_PREPARSED_DATA</a> structure.


## -returns



**HidD_GetPreparsedData** returns **TRUE** if it succeeds; otherwise, it returns **FALSE**. Use [**GetLastError**](https://docs.microsoft.com/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror) to get extended error information.




## -remarks



Only user-mode applications can call **HidD_GetPreparsedData**. Kernel-mode drivers can use an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_collection_descriptor">IOCTL_HID_GET_COLLECTION_DESCRIPTOR</a> request.

When an application no longer requires the preparsed data, it should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_freepreparseddata">HidD_FreePreparsedData</a> to free the preparsed data buffer.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_freepreparseddata">HidD_FreePreparsedData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_collection_descriptor">IOCTL_HID_GET_COLLECTION_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getpreparseddata">_HIDP_PREPARSED_DATA</a>
 

 

