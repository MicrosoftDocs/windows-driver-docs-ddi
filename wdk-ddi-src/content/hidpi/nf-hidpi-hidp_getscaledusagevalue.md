---
UID: NF:hidpi.HidP_GetScaledUsageValue
title: HidP_GetScaledUsageValue function (hidpi.h)
description: The HidP_GetScaledUsageValue routine returns the signed and scaled result of a HID control value extracted from a HID report.
old-location: hid\hidp_getscaledusagevalue.htm
tech.root: hid
ms.assetid: 0af1a3f2-b933-4232-865c-cccca53fd32e
ms.date: 04/30/2018
ms.keywords: HidP_GetScaledUsageValue, HidP_GetScaledUsageValue routine [Human Input Devices], hid.hidp_getscaledusagevalue, hidfunc_7fa22086-ab66-4c6b-a7de-65adce226b10.xml, hidpi/HidP_GetScaledUsageValue
ms.topic: function
f1_keywords:
 - "hidpi/HidP_GetScaledUsageValue"
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
- HidP_GetScaledUsageValue
product:
- Windows
targetos: Windows
req.typenames: 
---

# HidP_GetScaledUsageValue function


## -description


The <b>HidP_GetScaledUsageValue</b> routine returns the signed and scaled result of a HID control value extracted from a HID report.


## -parameters




### -param ReportType [in]

Specifies a <b>HIDP_REPORT_TYPE</b> enumerator value that identifies the type of HID report that contains the <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-usages">HID usage</a> value.


### -param UsagePage [in]

Specifies the usage page of the value to extract.


### -param LinkCollection [in]

Specifies the link collection identifier of the value to extract. A LinkCollection value of zero identifies the top-level collection.


### -param Usage [in]

Specifies the usage of the value to extract.


### -param UsageValue [out]

Pointer to the buffer in which the routine returns the signed and scaled value.


### -param PreparsedData [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/preparsed-data">preparsed data</a> of the <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection</a> that generated the report located at <i>Report</i>.


### -param Report [in]

Pointer to the report that contains the usage.


### -param ReportLength [in]

Specifies the length, in bytes, of the report located at <i>Report</i>.


## -returns



<b>HidP_GetScaledUsageValue</b> returns one of the following status values:

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
The routine successfully returned the value.

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
<dt><b>HIDP_STATUS_INVALID_REPORT_LENGTH</b></dt>
</dl>
</td>
<td width="60%">
The specified report length is not valid

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_BAD_LOG_PHY_VALUES</b></dt>
</dl>
</td>
<td width="60%">
The collection returned an illegal logical or physical value. To extract the value returned by the collection, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getusagevalue">HidP_GetUsageValue</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_NULL</b></dt>
</dl>
</td>
<td width="60%">
The current state of the scaled value from the collection is less than the logical minimum or is greater than the logical maximum, and the scaled value has a <b>NULL</b> state.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_VALUE_OUT_OF_RANGE</b></dt>
</dl>
</td>
<td width="60%">
The current state of the scaled value data from the collection is less than the logical minimum or is greater than the logical maximum.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_USAGE_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The specified usage, usage page, or link collection cannot be found in any report supported by the specified top-level collection.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INCOMPATIBLE_REPORT_ID</b></dt>
</dl>
</td>
<td width="60%">
The specified value is not contained in the specified report, but is contained in another report supported by the specified top-level collection.

</td>
</tr>
</table>
 




## -remarks



The caller-allocated buffers supplied at <i>PreparsedData</i>, <i>UsageValue</i>, and<i> Report </i>must be allocated from nonpaged pool.

User-mode applications and kernel-mode drivers must use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getusagevaluearray">HidP_GetUsageValueArray</a> to extract data for a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/value-capability-arrays">usage value array</a>.

If the routine returns status HIDP_STATUS_BAD_LOG_PHY_VALUES, an application or driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getusagevalue">HidP_GetUsageValue</a> to extract the raw usage data.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getusagevalue">HidP_GetUsageValue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getusagevaluearray">HidP_GetUsageValueArray</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getpreparseddata">_HIDP_PREPARSED_DATA</a>
 

 

