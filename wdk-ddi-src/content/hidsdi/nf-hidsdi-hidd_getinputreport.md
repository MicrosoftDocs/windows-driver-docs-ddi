---
UID: NF:hidsdi.HidD_GetInputReport
title: HidD_GetInputReport function
author: windows-driver-content
description: The HidD_GetInputReport routine returns an input reports from a top-level collection.
old-location: hid\hidd_getinputreport.htm
old-project: hid
ms.assetid: 42e0a96b-2b0b-4d22-8c91-14457d02e9c7
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: HidD_GetInputReport, HidD_GetInputReport routine [Human Input Devices], hid.hidd_getinputreport, hidfunc_fdcd7a5b-6623-419f-abdf-de19370ee793.xml, hidsdi/HidD_GetInputReport
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
-	HidD_GetInputReport
product: Windows
targetos: Windows
req.typenames: HID_MINIDRIVER_REGISTRATION, *PHID_MINIDRIVER_REGISTRATION
---

# HidD_GetInputReport function


## -description


The <b>HidD_GetInputReport</b> routine returns an input reports from a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>.


## -syntax


````
BOOLEAN __stdcall HidD_GetInputReport(
  _In_  HANDLE HidDeviceObject,
  _Out_ PVOID  ReportBuffer,
  _In_  ULONG  ReportBufferLength
);
````


## -parameters




### -param HidDeviceObject [in]

Specifies an open handle to a top-level collection.


### -param ReportBuffer [out]

Pointer to a caller-allocated input report buffer that the caller uses to specify a HID report ID and <b>HidD_GetInputReport</b> uses to return the specified input report. 

For more information about this parameter, see the Remarks section.


### -param ReportBufferLength [in]

Specifies the size, in bytes, of the report buffer. The report buffer must be large enough to hold the input report -- excluding its report ID, if report IDs are used -- plus one additional byte that specifies a nonzero report ID or zero.


## -returns



<b>HidD_GetInputReport</b> returns <b>TRUE</b> if it succeeds; otherwise, it returns <b>FALSE</b>.




## -remarks



Before it calls the <b>HidD_GetInputReport</b> routine, the caller must do the following:

<ul>
<li>
If the <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> includes report IDs, the caller must set the first byte of the <i>ReportBuffer</i> parameter to a nonzero report ID.

</li>
<li>
If the <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> does not include report IDs, the caller must set the first byte of the <i>ReportBuffer</i> parameter to zero.



</li>
</ul>
The input report is returned in the <i>ReportBuffer</i>  parameter. Depending on the report ID, the caller parses the report by calling one of the following functions:

<ul>
<li>
<a href="..\hidpi\nf-hidpi-hidp_getbuttoncaps.md">HidP_GetButtonCaps</a>
</li>
<li>
<a href="..\hidpi\nf-hidpi-hidp_getdata.md">HidP_GetData</a>
</li>
<li>
<a href="..\hidpi\nf-hidpi-hidp_getextendedattributes.md">HidP_GetExtendedAttributes</a>
</li>
<li>
<a href="..\hidpi\nf-hidpi-hidp_getscaledusagevalue.md">HidP_GetScaledUsageValue</a>
</li>
<li>
<a href="..\hidpi\nf-hidpi-hidp_getspecificbuttoncaps.md">HidP_GetSpecificButtonCaps</a>
</li>
<li>
<a href="..\hidpi\nf-hidpi-hidp_getspecificvaluecaps.md">HidP_GetSpecificValueCaps</a>
</li>
<li>
<a href="..\hidpi\nf-hidpi-hidp_getusages.md">HidP_GetUsages</a>
</li>
<li>
<a href="..\hidpi\nf-hidpi-hidp_getusagesex.md">HidP_GetUsagesEx</a>
</li>
<li>
<a href="..\hidpi\nf-hidpi-hidp_getusagevalue.md">HidP_GetUsageValue</a>
</li>
<li>
<a href="..\hidpi\nf-hidpi-hidp_getusagevaluearray.md">HidP_GetUsageValueArray</a>
</li>
<li>
<a href="..\hidpi\nf-hidpi-hidp_getvaluecaps.md">HidP_GetValueCaps</a>
</li>
</ul>
For an example of how to parse a HID report, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=256119">HClient</a> sample application. This sample is located in the MSDN Code Gallery.

Only user-mode applications can call <b>HidD_GetInputReport</b>. Kernel-mode drivers can use an <a href="..\hidclass\ni-hidclass-ioctl_hid_get_input_report.md">IOCTL_HID_GET_INPUT_REPORT</a> request.


    For more information, see <a href="https://msdn.microsoft.com/10f8c3a1-ad60-4c99-a425-fa8c9a3be0e1">Interpreting HID Reports</a>.
    
   




## -see-also

<a href="..\hidclass\ni-hidclass-ioctl_hid_set_feature.md">IOCTL_HID_SET_FEATURE</a>



<a href="..\hidclass\ni-hidclass-ioctl_hid_get_input_report.md">IOCTL_HID_GET_INPUT_REPORT</a>



<a href="..\hidclass\ni-hidclass-ioctl_hid_get_feature.md">IOCTL_HID_GET_FEATURE</a>



<a href="..\hidsdi\nf-hidsdi-hidd_getfeature.md">HidD_GetFeature</a>



<a href="..\hidsdi\nf-hidsdi-hidd_setfeature.md">HidD_SetFeature</a>



<a href="..\hidclass\ni-hidclass-ioctl_hid_set_output_report.md">IOCTL_HID_SET_OUTPUT_REPORT</a>



<a href="..\hidsdi\nf-hidsdi-hidd_setoutputreport.md">HidD_SetOutputReport</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidD_GetInputReport routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

