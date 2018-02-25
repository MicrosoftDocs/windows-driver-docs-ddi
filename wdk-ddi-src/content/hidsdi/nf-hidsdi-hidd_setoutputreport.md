---
UID: NF:hidsdi.HidD_SetOutputReport
title: HidD_SetOutputReport function
author: windows-driver-content
description: The HidD_SetOutputReport routine sends an output report to a top-level collection.
old-location: hid\hidd_setoutputreport.htm
old-project: hid
ms.assetid: a4ec7a17-40c4-4812-a62a-585b3b486578
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , D, H, HidD_SetOutputReport, HidD_SetOutputReport routine [Human Input Devices], O, R, S, _, d, e, hid.hidd_setoutputreport, hidfunc_eb711fe9-fdf1-4757-90c1-6c4e115f3805.xml, hidsdi/HidD_SetOutputReport, i, o, p, r, t, u"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Hid.dll
apiname:
-	HidD_SetOutputReport
product: Windows
targetos: Windows
req.typenames: HID_MINIDRIVER_REGISTRATION, *PHID_MINIDRIVER_REGISTRATION
---

# HidD_SetOutputReport function


## -description


The <b>HidD_SetOutputReport</b> routine sends an output report to a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>.


## -syntax


````
BOOLEAN __stdcall HidD_SetOutputReport(
  _In_ HANDLE HidDeviceObject,
  _In_ PVOID  ReportBuffer,
  _In_ ULONG  ReportBufferLength
);
````


## -parameters




### -param HidDeviceObject [in]

Specifies an open handle to a top-level collection.


### -param ReportBuffer [in]

Pointer to a caller-allocated output report buffer that the caller uses to specify a report ID.

For more information about this parameter, see the Remarks section.


### -param ReportBufferLength [in]

Specifies the size, in bytes, of the report buffer. The report buffer must be large enough to hold the output report -- excluding its report ID, if report IDs are used -- plus one additional byte that specifies a nonzero report ID or zero.


## -returns



If <b>HidD_SetOutputReport</b> succeeds, it returns <b>TRUE</b>; otherwise, it returns <b>FALSE</b>.




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
<a href="..\hidpi\nf-hidpi-hidp_setdata.md">HidP_SetData</a>
</li>
<li>
<a href="..\hidpi\nf-hidpi-hidp_setscaledusagevalue.md">HidP_SetScaledUsageValue</a>
</li>
<li>
<a href="..\hidpi\nf-hidpi-hidp_setusages.md">HidP_SetUsages</a>
</li>
<li>
<a href="..\hidpi\nf-hidpi-hidp_setusagevalue.md">HidP_SetUsageValue</a>
</li>
<li>
<a href="..\hidpi\nf-hidpi-hidp_setusagevaluearray.md">HidP_SetUsageValueArray</a>
</li>
</ul>
</li>
</ul>
For an example of how to prepare and  a HID report and send it to a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=256119">HClient</a> sample application. This sample is located in the MSDN Code Gallery.

Only user-mode applications can call <b>HidD_SetOutputReport</b>. Kernel-mode drivers can use an <a href="..\hidclass\ni-hidclass-ioctl_hid_set_output_report.md">IOCTL_HID_SET_OUTPUT_REPORT</a> request.

For more information, see the following topics:


<a href="https://msdn.microsoft.com/a4571b79-847b-4db0-be02-ac2f922162bb">Sending HID Reports</a>



<a href="https://msdn.microsoft.com/10f8c3a1-ad60-4c99-a425-fa8c9a3be0e1">Interpreting HID Reports</a>





## -see-also

<a href="..\hidsdi\nf-hidsdi-hidd_setfeature.md">HidD_SetFeature</a>



<a href="..\hidsdi\nf-hidsdi-hidd_getinputreport.md">HidD_GetInputReport</a>



<a href="..\hidclass\ni-hidclass-ioctl_hid_set_output_report.md">IOCTL_HID_SET_OUTPUT_REPORT</a>



<a href="..\hidclass\ni-hidclass-ioctl_hid_get_input_report.md">IOCTL_HID_GET_INPUT_REPORT</a>



<a href="..\hidclass\ni-hidclass-ioctl_hid_get_feature.md">IOCTL_HID_GET_FEATURE</a>



<a href="..\hidsdi\nf-hidsdi-hidd_getfeature.md">HidD_GetFeature</a>



<a href="..\hidclass\ni-hidclass-ioctl_hid_set_feature.md">IOCTL_HID_SET_FEATURE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidD_SetOutputReport routine%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

