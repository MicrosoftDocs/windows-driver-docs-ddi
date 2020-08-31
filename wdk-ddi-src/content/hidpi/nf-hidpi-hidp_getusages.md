---
UID: NF:hidpi.HidP_GetUsages
title: HidP_GetUsages function (hidpi.h)
description: The HidP_GetUsages routine returns a list of all the HID control button usages that are on a specified usage page and are set to ON in a HID report.
old-location: hid\hidp_getusages.htm
tech.root: hid
ms.assetid: e35ae7c6-2cf4-4f20-bb00-7f33ae133118
ms.date: 04/30/2018
keywords: ["HidP_GetUsages function"]
ms.keywords: HidP_GetUsages, HidP_GetUsages routine [Human Input Devices], hid.hidp_getusages, hidfunc_ed08f7c0-5435-417a-958f-34a6cbb1f541.xml, hidpi/HidP_GetUsages
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
targetos: Windows
req.typenames: 
f1_keywords:
 - HidP_GetUsages
 - hidpi/HidP_GetUsages
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Hidparse.lib
 - Hidparse.dll
api_name:
 - HidP_GetUsages
---

# HidP_GetUsages function


## -description

The <b>HidP_GetUsages </b>routine returns a list of all the HID control button <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-usages">usages</a> that are on a specified <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-usages">usage page</a> and are set to ON in a HID report.

## -parameters

### -param ReportType 

[in]
Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/ne-hidpi-_hidp_report_type">HIDP_REPORT_TYPE</a> enumerator value that identifies the report type.

### -param UsagePage 

[in]
Specifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-usages">usage page</a> of the button usages. The routine only returns information about buttons on this usage page.

### -param LinkCollection 

[in]
Specifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/link-collections">link collection</a> of the button usages. If <i>LinkCollection</i> is nonzero, the routine only returns information about the buttons that this link collection contains; otherwise, if <i>LinkCollection</i> is zero, the routine returns information about all the buttons in the <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection</a> associated with <i>PreparsedData</i>.

### -param UsageList 

[out]
Pointer to a caller-allocated buffer that the routine uses to return the usages of all buttons that are set to ON and belong to the usage page specified by <i>UsagePage</i>.

### -param UsageLength 

[in, out]
Specifies, on input, the length, in array elements, of the <i>UsageList</i> buffer. Specifies, on output, the number of buttons that are set to ON on the specified usage page.

### -param PreparsedData 

[in]
Pointer to a top-level collection's <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/preparsed-data">preparsed data</a>.

### -param Report 

[out]
Pointer to a report.

### -param ReportLength 

[in]
Specifies the length, in bytes, of the report located at <i>Report</i>.

## -returns

<b>HidP_GetUsages</b> returns one of the following status values:

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
The routine successfully returned all button usages set to ON.

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
<dt><b>HIDP_STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The <i>UsageList</i> buffer is too small to hold all the usages that are currently set to ON on the specified usage page.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INCOMPATIBLE_REPORT_ID</b></dt>
</dl>
</td>
<td width="60%">
The collection contains buttons on the specified usage page in a report of the specified type, but there are no such usages in the specified report.

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
The collection does not contain any buttons on the specified usage page in any report of the specified report type.

</td>
</tr>
</table>

## -remarks

User-mode applications and kernel-mode drivers call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_maxusagelistlength">HidP_MaxUsageListLength</a> to determine the maximum number of buttons that can be returned for specified report type. Alternatively, applications or drivers can call <b>HidP_GetUsages</b> and set *(\*UsageLength)* to zero to return the required length in <i>UsageLength</i>. In other words, *UsageLength* should be a valid pointer that points to a ULONG value **0** to get the required length.

Applications or drivers determine the required report length from the <i>Xxx</i><b>ReportByteLength</b> members in a top-level collection's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_caps">HIDP_CAPS</a> structure.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hdpi-h-macros">HidP_GetButtons</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hdpi-h-macros">HidP_GetButtonsEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getcaps">HidP_GetCaps</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getscaledusagevalue">HidP_GetScaledUsageValue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getusagevalue">HidP_GetUsageValue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getusagevaluearray">HidP_GetUsageValueArray</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getusagesex">HidP_GetUsagesEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_maxusagelistlength">HidP_MaxUsageListLength</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getpreparseddata">_HIDP_PREPARSED_DATA</a>

