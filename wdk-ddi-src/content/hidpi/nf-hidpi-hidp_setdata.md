---
UID: NF:hidpi.HidP_SetData
title: HidP_SetData function (hidpi.h)
description: The HidP_SetData routine sets a specified set of HID control button and value usages in a HID report.
old-location: hid\hidp_setdata.htm
tech.root: hid
ms.assetid: 41f7c240-4e50-4d6c-82aa-902ab05bf715
ms.date: 04/30/2018
keywords: ["HidP_SetData function"]
ms.keywords: HidP_SetData, HidP_SetData routine [Human Input Devices], hid.hidp_setdata, hidfunc_4b2f18db-e7a2-432d-abd6-51240a0ffc91.xml, hidpi/HidP_SetData
f1_keywords:
 - "hidpi/HidP_SetData"
 - "HidP_SetData"
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Hidparse.lib
- Hidparse.dll
api_name:
- HidP_SetData
product:
- Windows
targetos: Windows
req.typenames: 
---

# HidP_SetData function


## -description


The <b>HidP_SetData</b> routine sets a specified set of HID control button and value usages in a HID report.


## -parameters




### -param ReportType [in]

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/ne-hidpi-_hidp_report_type">HIDP_REPORT_TYPE</a> enumerator value that indicates the type of HID report located at <i>Report</i>.


### -param DataList [in, out]

Pointer to a caller-allocated array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_data">HIDP_DATA</a> structures that specify which buttons and usage values to set.


### -param DataLength [in, out]

Specifies, on input, the number of members in the <i>DataList</i> array. For information about the output value, see the Remarks section.


### -param PreparsedData [in]

Pointer to a top-level's <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/preparsed-data">preparsed data</a>.


### -param Report [in]

Pointer to a HID report.


### -param ReportLength [in]

Specifies the size, in bytes, of the HID report located at <i>Report</i>, which must be equal to the report length for the specified report type that <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getcaps">HidP_GetCaps</a> returns in a collection's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_caps">HIDP_CAPS</a> structure.


## -returns



<b>HidP_SetData</b> returns HIDP_STATUS_SUCCESS if it successfully sets all the control data specified by <i>DataList</i>.

<b>HidP_SetData</b> returns one of the following status values if one of the input parameters is not valid:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INVALID_PREPARSED_DATA</b></dt>
</dl>
</td>
<td width="60%">
The preparsed data specified by <i>PreparsedData</i> is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INVALID_REPORT_LENGTH</b></dt>
</dl>
</td>
<td width="60%">
The size, in bytes, of the HID report is not equal to the length specified in the collection's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_caps">HIDP_CAPS</a> structure for the specified report type.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INVALID_REPORT_TYPE</b></dt>
</dl>
</td>
<td width="60%">
<i>ReportType</i> is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_REPORT_DOES_NOT_EXIST</b></dt>
</dl>
</td>
<td width="60%">
The collection does not contain a report of the specified type.

</td>
</tr>
</table>
 

HidP_SetData returns one of the following error values if one of the specified button or usage values could not be set:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
A button in an array was not set to ON (1) because all the array fields are already used to index other buttons.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_BUTTON_NOT_PRESSED</b></dt>
</dl>
</td>
<td width="60%">
A DataList member specifies to set a button OFF (zero), but the button is already set to OFF.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_DATA_INDEX_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The data index of a DataList member is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INCOMPATIBLE_REPORT_ID</b></dt>
</dl>
</td>
<td width="60%">
A button or usage value is contained in a report, but it is not in the specified report.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_IS_VALUE_ARRAY</b></dt>
</dl>
</td>
<td width="60%">
A data index specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/value-capability-arrays">usage value array</a>.

</td>
</tr>
</table>
 




## -remarks



Except for usage value arrays, a user-mode application or kernel-mode driver can use <b>HidP_SetData</b> to set buttons and usage values in a report. To set a usage value array, an application or driver must use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_setusagevaluearray">HidP_SetUsageValueArray</a>.

<b>HidP_SetData</b> sets the output value of <i>DataLength</i> as follows:



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_data">HIDP_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getdata">HidP_GetData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hdpi-h-macros">HidP_SetButtons</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_setusagevaluearray">HidP_SetUsageValueArray</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_setusages">HidP_SetUsages</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hdpi-h-macros">HidP_UnsetButtons</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_unsetusages">HidP_UnsetUsages</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getpreparseddata">_HIDP_PREPARSED_DATA</a>
 

 

