---
UID: NF:hidsdi.HidD_SetOutputReport
title: HidD_SetOutputReport function (hidsdi.h)
description: The HidD_SetOutputReport routine sends an output report to a top-level collection.
old-location: hid\hidd_setoutputreport.htm
tech.root: hid
ms.assetid: a4ec7a17-40c4-4812-a62a-585b3b486578
ms.date: 06/19/2019
ms.keywords: HidD_SetOutputReport, HidD_SetOutputReport routine [Human Input Devices], hid.hidd_setoutputreport, hidfunc_eb711fe9-fdf1-4757-90c1-6c4e115f3805.xml, hidsdi/HidD_SetOutputReport
ms.topic: function
req.header: hidsdi.h
req.include-header: Hidsdi.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
- HidD_SetOutputReport
product:
- Windows
targetos: Windows
req.typenames: 
---

# HidD_SetOutputReport function


## -description


The <b>HidD_SetOutputReport</b> routine sends an output report to a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>.


## -parameters




### -param HidDeviceObject [in]

Specifies an open handle to a top-level collection.


### -param ReportBuffer [in]

Pointer to a caller-allocated output report buffer that the caller uses to specify a report ID.

For more information about this parameter, see the Remarks section.


### -param ReportBufferLength [in]

Specifies the size, in bytes, of the report buffer. The report buffer must be large enough to hold the output report -- excluding its report ID, if report IDs are used -- plus one additional byte that specifies a nonzero report ID or zero.


## -returns



If <b>HidD_SetOutputReport</b> succeeds, it returns <b>TRUE</b>; otherwise, it returns <b>FALSE</b>. Use [**GetLastError**](https://docs.microsoft.com/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror) to get extended error information.




## -remarks



Before it calls the <b>HidD_SetOutputReport</b> routine, the caller must do the following:

<ul>
<li>
If the <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> includes report IDs, the caller must set the first byte of the <i>ReportBuffer</i> parameter to a nonzero report ID.

</li>
<li>
If the <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> does not include report IDs, the caller must set the first byte of the <i>ReportBuffer</i> parameter to zero.



</li>
<li>
The output report is referenced by the <i>ReportBuffer</i> parameter. Depending on the report ID, the caller prepares the report by calling one of the following functions:

<ul>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539783">HidP_SetData</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539787">HidP_SetScaledUsageValue</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539792">HidP_SetUsages</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539797">HidP_SetUsageValue</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539801">HidP_SetUsageValueArray</a>
</li>
</ul>
</li>
</ul>
For an example of how to prepare and  a HID report and send it to a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=256119">HClient</a> sample application. This sample is located in the MSDN Code Gallery.

Only user-mode applications can call <b>HidD_SetOutputReport</b>. Kernel-mode drivers can use an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541196">IOCTL_HID_SET_OUTPUT_REPORT</a> request.

For more information, see the following topics:


<a href="https://msdn.microsoft.com/a4571b79-847b-4db0-be02-ac2f922162bb">Sending HID Reports</a>



<a href="https://msdn.microsoft.com/10f8c3a1-ad60-4c99-a425-fa8c9a3be0e1">Interpreting HID Reports</a>





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538910">HidD_GetFeature</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538945">HidD_GetInputReport</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539684">HidD_SetFeature</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541100">IOCTL_HID_GET_FEATURE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541126">IOCTL_HID_GET_INPUT_REPORT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541176">IOCTL_HID_SET_FEATURE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541196">IOCTL_HID_SET_OUTPUT_REPORT</a>
 

 

