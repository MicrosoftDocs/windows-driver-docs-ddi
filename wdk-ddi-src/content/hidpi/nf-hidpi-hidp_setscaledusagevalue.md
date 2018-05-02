---
UID: NF:hidpi.HidP_SetScaledUsageValue
title: HidP_SetScaledUsageValue function
author: windows-driver-content
description: The HidP_SetScaledUsageValue routine converts a signed and scaled physical number to a HID usage's logical value, and sets the usage value in a specified HID report.
old-location: hid\hidp_setscaledusagevalue.htm
old-project: hid
ms.assetid: 0b863b69-b736-49dd-94a9-283480d035be
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: HidP_SetScaledUsageValue, HidP_SetScaledUsageValue routine [Human Input Devices], hid.hidp_setscaledusagevalue, hidfunc_0fcd2d78-aae7-4d56-a930-9bf0e4a417bf.xml, hidpi/HidP_SetScaledUsageValue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hidpi.h
req.include-header: Hidpi.h
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
req.lib: Hidparse.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Hidparse.lib
-	Hidparse.dll
api_name:
-	HidP_SetScaledUsageValue
product: Windows
targetos: Windows
req.typenames: 
---

# HidP_SetScaledUsageValue function


## -description


The <b>HidP_SetScaledUsageValue</b> routine converts a signed and scaled physical number to a <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">HID usage's</a> logical value, and sets the usage value in a specified HID report.


## -parameters




### -param ReportType [in]

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539774">HIDP_REPORT_TYPE</a> enumerator value that indicates the type of HID report located at <i>Report</i>.


### -param UsagePage [in]

Specifies the <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage page</a> of a usage.


### -param LinkCollection [in]

Specifies the <a href="https://msdn.microsoft.com/3f934661-c33c-4c08-82ac-ee2e0f519c8e">link collection</a> that contains the usage. If <i>LinkCollection</i> is nonzero, the routine only sets the usage, if one exists, in this link collection. If <i>LinkCollection</i> is zero, the routine sets the first usage it finds in the <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> associated with <i>PreparsedData</i>.


### -param Usage [in]

Specifies the usage.


### -param UsageValue [in]

Specifies the signed and scaled physical number, which the routine converts to the usage's logical value.


### -param PreparsedData [in]

Pointer to a top-level's <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a>.


### -param Report [in, out]

Pointer to a HID report.


### -param ReportLength [in]

Specifies the size, in bytes, of the HID report located at <i>Report</i>, which must be equal to the report length for the specified report type that <a href="https://msdn.microsoft.com/library/windows/hardware/ff539715">HidP_GetCaps</a> returns in a collection's <a href="https://msdn.microsoft.com/library/windows/hardware/ff539697">HIDP_CAPS</a> structure.


## -returns



<b>HidP_SetScaledUsageValue</b> returns one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The routine successfully set the usage value.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_BAD_LOG_PHY_VALUES</b></dt>
</dl>
</td>
<td width="60%">
The usage has an illegal logical or physical range that prevents scaling.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_VALUE_OUT_OF_RANGE</b></dt>
</dl>
</td>
<td width="60%">
The specified physical value is out-of-range and the usage does not have null value.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INVALID_REPORT_LENGTH</b></dt>
</dl>
</td>
<td width="60%">
The report length is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INVALID_REPORT_TYPE</b></dt>
</dl>
</td>
<td width="60%">
The specified report type is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INCOMPATIBLE_REPORT_ID</b></dt>
</dl>
</td>
<td width="60%">
The usage does not exist in the specified report, but it does exist in a different report of the specified type.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INVALID_PREPARSED_DATA</b></dt>
</dl>
</td>
<td width="60%">
The preparsed data is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_USAGE_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The usage does not exist in any report of the specified report type.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_NULL</b></dt>
</dl>
</td>
<td width="60%">
The specified physical value is out-of-range, the usage has a null value, and the routine set the null value.

</td>
</tr>
</table>
 




## -remarks



<b>HidP_SetScaledUsageValue</b> sets the sign bit.

If the routine returns HIDP_STATUS_INCOMPATIBLE_REPORT_ID, the specified report does contain the usage. However, a user-mode application or kernel-mode driver can set the usage in a zero-initialized report. See <a href="https://msdn.microsoft.com/14229315-3928-4421-a8d8-c3f7837bf1c3">Initializing HID Reports</a>.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539697">HIDP_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539774">HIDP_REPORT_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539715">HidP_GetCaps</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539797">HidP_SetUsageValue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539801">HidP_SetUsageValueArray</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a>
 

 

