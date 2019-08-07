---
UID: NF:hidpi.HidP_SetUsageValueArray
title: HidP_SetUsageValueArray function (hidpi.h)
description: The HidP_SetUsageValueArray routine sets a HID control usage value array in a specified HID report.
old-location: hid\hidp_setusagevaluearray.htm
tech.root: hid
ms.assetid: 8c18c224-6d55-405d-87ec-cca99d702713
ms.date: 04/30/2018
ms.keywords: HidP_SetUsageValueArray, HidP_SetUsageValueArray routine [Human Input Devices], hid.hidp_setusagevaluearray, hidfunc_08ebfd84-e1da-4eb8-8741-ec2b16b488c9.xml, hidpi/HidP_SetUsageValueArray
ms.topic: function
f1_keywords:
 - "hidpi/HidP_SetUsageValueArray"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Hidparse.lib
- Hidparse.dll
api_name:
- HidP_SetUsageValueArray
product:
- Windows
targetos: Windows
req.typenames: 
---

# HidP_SetUsageValueArray function


## -description


The <b>HidP_SetUsageValueArray</b> routine sets a HID control <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/value-capability-arrays">usage value array</a> in a specified HID report.


## -parameters




### -param ReportType [in]

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/ne-hidpi-_hidp_report_type">HIDP_REPORT_TYPE</a> enumerator value that indicates the type of HID report located at <i>Report</i>.


### -param UsagePage [in]

Specifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-usages">usage page</a> of a usage.


### -param LinkCollection [in]

Specifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/link-collections">link collection</a> that contains the usage. If <i>LinkCollection</i> is nonzero, the routine only sets the usage, if one exists, in this link collection. If <i>LinkCollection</i> is zero, the routine sets the first usage it finds in the <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection</a> associated with <i>PreparsedData</i>.


### -param Usage [in]

Specifies the usage.


### -param UsageValue [in]

Pointer to a caller-allocated buffer that contains the data associated with the usage value array.


### -param UsageValueByteLength [in]

Specifies the length, in bytes, of the <i>UsageValue</i> buffer.


### -param PreparsedData [in]

Pointer to a top-level's <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/preparsed-data">preparsed data</a>.


### -param Report [in, out]

Pointer to a HID report.


### -param ReportLength [in]

Specifies the size, in bytes, of the HID report located at <i>Report</i>, which must be equal to the report length for the specified report type that <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/nf-hidpi-hidp_getcaps">HidP_GetCaps</a> returns in a collection's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/ns-hidpi-_hidp_caps">HIDP_CAPS</a> structure.


## -returns



<b>HidP_SetUsageValueArray</b> returns one of the following status values:

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
<dt><b>HIDP_STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The size, in bytes, of the <i>UsageValue</i> buffer is too small.

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
<dt><b>HIDP_STATUS_NOT_VALUE_ARRAY</b></dt>
</dl>
</td>
<td width="60%">
The specified usage is not a usage value array.

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
<dt><b>HIDP_STATUS_REPORT_DOES_NOT_EXIST</b></dt>
</dl>
</td>
<td width="60%">
There are no reports of the specified type.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
The report size of data fields specified for the usage value array is not a multiple of eight bits.

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
</table>
 




## -remarks



The required size, in bytes, of the <i>UsageValue</i> buffer is determined by multiplying together the <b>BitSize</b> and <b>ReportCount</b> members of the usage value array's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/ns-hidpi-_hidp_value_caps">HIDP_VALUE_CAPS</a> structure, and rounding the result up to the nearest byte.

<b>HidP_SetUsageValueArray</b> only supports usage value arrays where each data field of the array is a multiple of eight bits.

The caller must set the <i>UsageValue</i> buffer exactly as it should occur in the report.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/nf-hidpi-hidp_setscaledusagevalue">HidP_SetScaledUsageValue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/nf-hidpi-hidp_setusagevalue">HidP_SetUsageValue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidsdi/nf-hidsdi-hidd_getpreparseddata">_HIDP_PREPARSED_DATA</a>
 

 

