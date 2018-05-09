---
UID: NF:hidpi.HidP_GetUsageValue
title: HidP_GetUsageValue function
author: windows-driver-content
description: The HidP_GetUsageValue routine extracts the data associated with a HID control value that matches the selection criteria in a HID report.
old-location: hid\hidp_getusagevalue.htm
old-project: hid
ms.assetid: 5f2d1536-4676-4afe-aa5c-08e7c74d1dd2
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: HidP_GetUsageValue, HidP_GetUsageValue routine [Human Input Devices], hid.hidp_getusagevalue, hidfunc_d046d7e6-bd4c-4d80-80a8-f8e2d000eeee.xml, hidpi/HidP_GetUsageValue
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
-	HidP_GetUsageValue
product:
- Windows
targetos: Windows
req.typenames: 
---

# HidP_GetUsageValue function


## -description


The <b>HidP_GetUsageValue</b> routine extracts the data associated with a HID control value that matches the selection criteria in a HID report.


## -parameters




### -param ReportType [in]

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539774">HIDP_REPORT_TYPE</a> enumerator value that identifies the report type.


### -param UsagePage [in]

Specifies the value's <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage page</a>.


### -param LinkCollection [in]

Specifies the <a href="https://msdn.microsoft.com/3f934661-c33c-4c08-82ac-ee2e0f519c8e">link collection</a> that contains the value. If <i>LinkCollection</i> is nonzero, the routine only searches for the usage in this link collection; otherwise, if <i>LinkCollection</i> is zero, the routine searches for the usage in the <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> associated with <i>PreparsedData</i>.


### -param Usage [in]

Specifies the usage of the value.


### -param UsageValue [out]

Pointer to a buffer in which the routine returns the value data.


### -param PreparsedData [in]

Pointer to a top-level collection's <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a>.


### -param Report [in]

Pointer to a report that contains values.


### -param ReportLength [in]

Specifies the length, in bytes, of the report located at <i>Report</i>.


## -returns



<b>HidP_GetUsageValue</b> returns one of the following status values:

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
The routine successfully returned the value data.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_INVALID_REPORT_LENGTH</b></dt>
</dl>
</td>
<td width="60%">
The report length is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_INVALID_REPORT_TYPE</b></dt>
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
The collection contains a value on the specified usage page in a report of the specified type, but there are no such usages in the specified report.

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
The collection does not contain a value on the specified usage page in any report of the specified report type.

</td>
</tr>
</table>
 




## -remarks



<b>HidP_GetUsageValue</b> does not sign or scale the value. To extract a signed value, use <b>HidP_GetScaledUsageValue</b>. To manually assign the sign bit, the position of the sign bit can be determined from the information in a value's <a href="https://msdn.microsoft.com/library/windows/hardware/ff539832">HIDP_VALUE_CAPS</a> structure.

<b>HidP_GetUsageValue</b> is designed to extract a usage value for a usage whose report count is 1. If the specified usage has a report count greater than 1, the usage is part of a <a href="https://msdn.microsoft.com/d447dda6-a1e5-4e57-b06f-f79f8662c236">usage value array</a>. <b>HidP_GetUsageValue</b> only returns the first data item in a usage value array. To extract all data items in a usage value array, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff539750">HidP_GetUsageValueArray</a>. 

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539832">HIDP_VALUE_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539708">HidP_GetButtons</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539712">HidP_GetButtonsEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539715">HidP_GetCaps</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539729">HidP_GetScaledUsageValue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539750">HidP_GetUsageValueArray</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539742">HidP_GetUsages</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539745">HidP_GetUsagesEx</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a>
 

 

