---
UID: NF:hidsdi.HidD_GetFeature
title: HidD_GetFeature function
author: windows-driver-content
description: The HidD_GetFeature routine returns a feature report from a specified top-level collection.
old-location: hid\hidd_getfeature.htm
old-project: hid
ms.assetid: e6a01367-981a-4b44-97a8-4cb37f9753fc
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: HidD_GetFeature, HidD_GetFeature routine [Human Input Devices], hid.hidd_getfeature, hidfunc_2992bcaf-4ca6-4b6f-9a85-d0add8c7fe99.xml, hidsdi/HidD_GetFeature
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
-	HidD_GetFeature
product:
- Windows
targetos: Windows
req.typenames: HID_MINIDRIVER_REGISTRATION, *PHID_MINIDRIVER_REGISTRATION
---

# HidD_GetFeature function


## -description


The <b>HidD_GetFeature</b> routine returns a feature report from a specified <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>.


## -parameters




### -param HidDeviceObject [in]

Specifies an open handle to a top-level collection.


### -param ReportBuffer [out]

Pointer to a caller-allocated HID report buffer that the caller uses to specify a report ID. <b>HidD_GetFeature</b> uses <i>ReportBuffer</i> to return the specified feature report. 

For more information about this parameter, see the Remarks section.


### -param ReportBufferLength [in]

Specifies the size, in bytes, of the report buffer. The report buffer must be large enough to hold the feature report -- excluding its report ID, if report IDs are used -- plus one additional byte that specifies a nonzero report ID or zero.


## -returns



If <b>HidD_GetFeature</b> succeeds, it returns <b>TRUE</b>; otherwise, it returns <b>FALSE</b>.




## -remarks



Before it calls the <b>HidD_GetFeature</b> routine, the caller must do the following:

<ul>
<li>
If the <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> includes report IDs, the caller must set the first byte of the <i>ReportBuffer</i> parameter to a nonzero report ID.

</li>
<li>
If the <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> does not include report IDs, the caller must set the first byte of the <i>ReportBuffer</i> parameter to zero.



</li>
</ul>
The feature report is returned in the <i>ReportBuffer</i>  parameter. Depending on the report ID, the caller parses the report by calling one of the following functions:

<ul>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539707">HidP_GetButtonCaps</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539718">HidP_GetData</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539721">HidP_GetExtendedAttributes</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539729">HidP_GetScaledUsageValue</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539733">HidP_GetSpecificButtonCaps</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539737">HidP_GetSpecificValueCaps</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539742">HidP_GetUsages</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539745">HidP_GetUsagesEx</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539748">HidP_GetUsageValue</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539750">HidP_GetUsageValueArray</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539754">HidP_GetValueCaps</a>
</li>
</ul>
For an example of how to parse a HID report, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=256119">HClient</a> sample application. This sample is located in the MSDN Code Gallery.

Only user-mode applications can call <b>HidD_GetFeature</b>. Kernel-mode drivers can use an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541100">IOCTL_HID_GET_FEATURE</a> request.

For more information, see the following topics:


<a href="https://msdn.microsoft.com/b6312dce-39af-4fff-b17d-4a50b9ab823b">Obtaining HID Reports</a>



<a href="https://msdn.microsoft.com/10f8c3a1-ad60-4c99-a425-fa8c9a3be0e1">Interpreting HID Reports</a>





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538945">HidD_GetInputReport</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539684">HidD_SetFeature</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539690">HidD_SetOutputReport</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541100">IOCTL_HID_GET_FEATURE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541126">IOCTL_HID_GET_INPUT_REPORT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541176">IOCTL_HID_SET_FEATURE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541196">IOCTL_HID_SET_OUTPUT_REPORT</a>
 

 

