---
UID: NF:hidsdi.HidD_FreePreparsedData
title: HidD_FreePreparsedData function
author: windows-driver-content
description: The HidD_FreePreparsedData routine releases the resources that the HID class driver allocated to hold a top-level collection's preparsed data.
old-location: hid\hidd_freepreparseddata.htm
old-project: hid
ms.assetid: 71e2f946-706d-41bc-9d9c-d63230877e48
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: hidsdi/HidD_FreePreparsedData, hidfunc_2ca8b6ee-b391-40ac-bd0e-491089d7ed06.xml, HidD_FreePreparsedData routine [Human Input Devices], hid.hidd_freepreparseddata, HidD_FreePreparsedData
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Hid.dll
apiname:
-	HidD_FreePreparsedData
product: Windows
targetos: Windows
req.typenames: "*PHID_MINIDRIVER_REGISTRATION, HID_MINIDRIVER_REGISTRATION"
---

# HidD_FreePreparsedData function


## -description


The <b>HidD_FreePreparsedData</b> routine releases the resources that the HID class driver allocated to hold a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection's</a> <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a>.


## -syntax


````
BOOLEAN __stdcall HidD_FreePreparsedData(
  _In_ PHIDP_PREPARSED_DATA PreparsedData
);
````


## -parameters




#### - PreparsedData [in]

Pointer to the buffer, returned by <a href="..\hidsdi\nf-hidsdi-hidd_getpreparseddata.md">HidD_GetPreparsedData</a>, that is freed.


## -returns


<b>HidD_FreePreparsedData</b> returns <b>TRUE</b> if it succeeds. Otherwise, it returns <b>FALSE</b> if the buffer was not a preparsed data buffer.



## -remarks


Only user-mode applications can call <b>HidD_FreePreparsedData</b>.

To obtain a collection's preparsed data, use <a href="..\hidsdi\nf-hidsdi-hidd_getpreparseddata.md">HidD_GetPreparsedData</a>.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>.



## -see-also

<a href="..\hidsdi\nf-hidsdi-hidd_getpreparseddata.md">HidD_GetPreparsedData</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidD_FreePreparsedData routine%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

