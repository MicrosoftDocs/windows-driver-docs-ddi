---
UID: NF:hidsdi.HidD_SetFeature
title: HidD_SetFeature function (hidsdi.h)
description: The HidD_SetFeature routine sends a feature report to a top-level collection.
old-location: hid\hidd_setfeature.htm
tech.root: hid
ms.assetid: 69b7d775-e689-4010-8c83-f9e393d692be
ms.date: 06/19/2019
ms.keywords: HidD_SetFeature, HidD_SetFeature routine [Human Input Devices], hid.hidd_setfeature, hidfunc_f34ed05a-c8c1-44e3-ab94-a8df000aac7d.xml, hidsdi/HidD_SetFeature
f1_keywords:
 - "hidsdi/HidD_SetFeature"
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
- HidD_SetFeature
product:
- Windows
targetos: Windows
req.typenames: 
---

# HidD_SetFeature function


## -description


The <b>HidD_SetFeature</b> routine sends a feature report to a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection</a>.


## -parameters




### -param HidDeviceObject [in]

Specifies an open handle to a top-level collection.


### -param ReportBuffer [in]

Pointer to a caller-allocated feature report buffer that the caller uses to specify a HID report ID.

For more information about this parameter, see the <b>Remarks</b> section.


### -param ReportBufferLength [in]

Specifies the size, in bytes, of the report buffer. The report buffer must be large enough to hold the feature report -- excluding its report ID, if report IDs are used -- plus one additional byte that specifies a nonzero report ID or zero.


## -returns



If <b>HidD_SetFeature</b> succeeds, it returns <b>TRUE</b>; otherwise, it returns <b>FALSE</b>. Use [**GetLastError**](https://docs.microsoft.com/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror) to get extended error information.




## -remarks



Before it calls the <b>HidD_SetFeature</b> routine, the caller must do the following:

<ul>
<li>
If the <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection</a> includes report IDs, the caller must set the first byte of the <i>ReportBuffer</i> parameter to a nonzero report ID.

</li>
<li>
If the <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection</a> does not include report IDs, the caller must set the first byte of the <i>ReportBuffer</i> parameter to zero.



</li>
<li>
The feature report is referenced by the <i>ReportBuffer</i> parameter. Depending on the report ID, the caller prepares the report by calling one of the following functions:

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

Only user-mode applications can call <b>HidD_SetFeature</b>. Kernel-mode drivers can use an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_set_output_report">IOCTL_HID_SET_OUTPUT_REPORT</a> request.

For more information, see the following topics:


<a href="https://docs.microsoft.com/windows-hardware/drivers/hid/sending-hid-reports">Sending HID Reports</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/hid/interpreting-hid-reports">Interpreting HID Reports</a>





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getfeature">HidD_GetFeature</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getinputreport">HidD_GetInputReport</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_setoutputreport">HidD_SetOutputReport</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_feature">IOCTL_HID_GET_FEATURE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_input_report">IOCTL_HID_GET_INPUT_REPORT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_set_feature">IOCTL_HID_SET_FEATURE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_set_output_report">IOCTL_HID_SET_OUTPUT_REPORT</a>
 

 

