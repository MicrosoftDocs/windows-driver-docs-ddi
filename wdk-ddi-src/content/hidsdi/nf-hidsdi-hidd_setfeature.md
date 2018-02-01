---
UID: NF:hidsdi.HidD_SetFeature
title: HidD_SetFeature function
author: windows-driver-content
description: The HidD_SetFeature routine sends a feature report to a top-level collection.
old-location: hid\hidd_setfeature.htm
old-project: hid
ms.assetid: 69b7d775-e689-4010-8c83-f9e393d692be
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: hid.hidd_setfeature, HidD_SetFeature, HidD_SetFeature routine [Human Input Devices], hidsdi/HidD_SetFeature, hidfunc_f34ed05a-c8c1-44e3-ab94-a8df000aac7d.xml
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
-	HidD_SetFeature
product: Windows
targetos: Windows
req.typenames: "*PHID_MINIDRIVER_REGISTRATION, HID_MINIDRIVER_REGISTRATION"
---

# HidD_SetFeature function


## -description


The <b>HidD_SetFeature</b> routine sends a feature report to a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>.


## -syntax


````
BOOLEAN __stdcall HidD_SetFeature(
  _In_ HANDLE HidDeviceObject,
  _In_ PVOID  ReportBuffer,
  _In_ ULONG  ReportBufferLength
);
````


## -parameters




### -param HidDeviceObject [in]

Specifies an open handle to a top-level collection.


### -param ReportBuffer [in]

Pointer to a caller-allocated feature report buffer that the caller uses to specify a HID report ID.

For more information about this parameter, see the <b>Remarks</b> section.


### -param ReportBufferLength [in]

Specifies the size, in bytes, of the report buffer. The report buffer must be large enough to hold the feature report -- excluding its report ID, if report IDs are used -- plus one additional byte that specifies a nonzero report ID or zero.


## -returns


If <b>HidD_SetFeature</b> succeeds, it returns <b>TRUE</b>; otherwise, it returns <b>FALSE</b>.



## -remarks


Before it calls the <b>HidD_SetFeature</b> routine, the caller must do the following:
<ul>
<li>
If the <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> includes report IDs, the caller must set the first byte of the <i>ReportBuffer</i> parameter to a nonzero report ID.

</li>
<li>
If the <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> does not include report IDs, the caller must set the first byte of the <i>ReportBuffer</i> parameter to zero.



</li>
<li>
The feature report is referenced by the <i>ReportBuffer</i> parameter. Depending on the report ID, the caller prepares the report by calling one of the following functions:

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
</ul>For an example of how to prepare and  a HID report and send it to a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=256119">HClient</a> sample application. This sample is located in the MSDN Code Gallery.

Only user-mode applications can call <b>HidD_SetFeature</b>. Kernel-mode drivers can use an <a href="..\hidclass\ni-hidclass-ioctl_hid_set_output_report.md">IOCTL_HID_SET_OUTPUT_REPORT</a> request.

For more information, see the following topics:


<a href="https://msdn.microsoft.com/a4571b79-847b-4db0-be02-ac2f922162bb">Sending HID Reports</a>



<a href="https://msdn.microsoft.com/10f8c3a1-ad60-4c99-a425-fa8c9a3be0e1">Interpreting HID Reports</a>




## -see-also

<a href="..\hidclass\ni-hidclass-ioctl_hid_set_feature.md">IOCTL_HID_SET_FEATURE</a>

<a href="..\hidsdi\nf-hidsdi-hidd_setoutputreport.md">HidD_SetOutputReport</a>

<a href="..\hidclass\ni-hidclass-ioctl_hid_get_input_report.md">IOCTL_HID_GET_INPUT_REPORT</a>

<a href="..\hidclass\ni-hidclass-ioctl_hid_set_output_report.md">IOCTL_HID_SET_OUTPUT_REPORT</a>

<a href="..\hidclass\ni-hidclass-ioctl_hid_get_feature.md">IOCTL_HID_GET_FEATURE</a>

<a href="..\hidsdi\nf-hidsdi-hidd_getfeature.md">HidD_GetFeature</a>

<a href="..\hidsdi\nf-hidsdi-hidd_getinputreport.md">HidD_GetInputReport</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidD_SetFeature routine%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

