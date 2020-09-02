---
UID: NF:hidsdi.HidD_SetOutputReport
title: HidD_SetOutputReport function (hidsdi.h)
description: The HidD_SetOutputReport routine sends an output report to a top-level collection.
old-location: hid\hidd_setoutputreport.htm
tech.root: hid
ms.assetid: a4ec7a17-40c4-4812-a62a-585b3b486578
ms.date: 06/19/2019
keywords: ["HidD_SetOutputReport function"]
ms.keywords: HidD_SetOutputReport, HidD_SetOutputReport routine [Human Input Devices], hid.hidd_setoutputreport, hidfunc_eb711fe9-fdf1-4757-90c1-6c4e115f3805.xml, hidsdi/HidD_SetOutputReport
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
targetos: Windows
req.typenames: 
f1_keywords:
 - HidD_SetOutputReport
 - hidsdi/HidD_SetOutputReport
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Hid.dll
api_name:
 - HidD_SetOutputReport
---

# HidD_SetOutputReport function


## -description

The <b>HidD_SetOutputReport</b> routine sends an output report to a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection</a>.

## -parameters

### -param HidDeviceObject 

[in]
Specifies an open handle to a top-level collection.

### -param ReportBuffer 

[in]
Pointer to a caller-allocated output report buffer that the caller uses to specify a report ID.

For more information about this parameter, see the Remarks section.

### -param ReportBufferLength 

[in]
Specifies the size, in bytes, of the report buffer. The report buffer must be large enough to hold the output report -- excluding its report ID, if report IDs are used -- plus one additional byte that specifies a nonzero report ID or zero.

## -returns

If <b>HidD_SetOutputReport</b> succeeds, it returns <b>TRUE</b>; otherwise, it returns <b>FALSE</b>. Use [**GetLastError**](https://docs.microsoft.com/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) to get extended error information.

## -remarks

Before it calls the <b>HidD_SetOutputReport</b> routine, the caller must do the following:

<ul>
<li>
If the <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection</a> includes report IDs, the caller must set the first byte of the <i>ReportBuffer</i> parameter to a nonzero report ID.

</li>
<li>
If the <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection</a> does not include report IDs, the caller must set the first byte of the <i>ReportBuffer</i> parameter to zero.



</li>
<li>
The output report is referenced by the <i>ReportBuffer</i> parameter. Depending on the report ID, the caller prepares the report by calling one of the following functions:

<ul>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_setdata">HidP_SetData</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_setscaledusagevalue">HidP_SetScaledUsageValue</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_setusages">HidP_SetUsages</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_setusagevalue">HidP_SetUsageValue</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_setusagevaluearray">HidP_SetUsageValueArray</a>
</li>
</ul>
</li>
</ul>
For an example of how to prepare and  a HID report and send it to a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection</a>, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=256119">HClient</a> sample application. This sample is located in the MSDN Code Gallery.

Only user-mode applications can call <b>HidD_SetOutputReport</b>. Kernel-mode drivers can use an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_set_output_report">IOCTL_HID_SET_OUTPUT_REPORT</a> request.

For more information, see the following topics:


<a href="https://docs.microsoft.com/windows-hardware/drivers/hid/sending-hid-reports">Sending HID Reports</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/hid/interpreting-hid-reports">Interpreting HID Reports</a>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getfeature">HidD_GetFeature</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getinputreport">HidD_GetInputReport</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_setfeature">HidD_SetFeature</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_feature">IOCTL_HID_GET_FEATURE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_input_report">IOCTL_HID_GET_INPUT_REPORT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_set_feature">IOCTL_HID_SET_FEATURE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_set_output_report">IOCTL_HID_SET_OUTPUT_REPORT</a>

