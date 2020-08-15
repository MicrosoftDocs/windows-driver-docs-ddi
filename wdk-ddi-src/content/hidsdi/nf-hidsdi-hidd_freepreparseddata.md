---
UID: NF:hidsdi.HidD_FreePreparsedData
title: HidD_FreePreparsedData function (hidsdi.h)
description: The HidD_FreePreparsedData routine releases the resources that the HID class driver allocated to hold a top-level collection's preparsed data.
old-location: hid\hidd_freepreparseddata.htm
tech.root: hid
ms.assetid: 71e2f946-706d-41bc-9d9c-d63230877e48
ms.date: 06/19/2019
keywords: ["HidD_FreePreparsedData function"]
ms.keywords: HidD_FreePreparsedData, HidD_FreePreparsedData routine [Human Input Devices], hid.hidd_freepreparseddata, hidfunc_2ca8b6ee-b391-40ac-bd0e-491089d7ed06.xml, hidsdi/HidD_FreePreparsedData
f1_keywords:
 - "hidsdi/HidD_FreePreparsedData"
 - "HidD_FreePreparsedData"
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
- HidD_FreePreparsedData
targetos: Windows
req.typenames: 
---

# HidD_FreePreparsedData function


## -description


The <b>HidD_FreePreparsedData</b> routine releases the resources that the HID class driver allocated to hold a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection's</a> <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/preparsed-data">preparsed data</a>.


## -parameters




### -param PreparsedData 
[in]
Pointer to the buffer, returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getpreparseddata">HidD_GetPreparsedData</a>, that is freed.


## -returns



<b>HidD_FreePreparsedData</b> returns <b>TRUE</b> if it succeeds. Otherwise, it returns <b>FALSE</b> if the buffer was not a preparsed data buffer. Use [**GetLastError**](https://docs.microsoft.com/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror) to get extended error information.




## -remarks



Only user-mode applications can call <b>HidD_FreePreparsedData</b>.

To obtain a collection's preparsed data, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getpreparseddata">HidD_GetPreparsedData</a>.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getpreparseddata">HidD_GetPreparsedData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getpreparseddata">_HIDP_PREPARSED_DATA</a>
 

 

