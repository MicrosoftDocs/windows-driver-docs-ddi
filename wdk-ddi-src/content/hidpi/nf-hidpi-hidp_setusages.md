---
UID: NF:hidpi.HidP_SetUsages
title: HidP_SetUsages function (hidpi.h)
description: The HidP_SetUsages routine sets specified HID control buttons ON (1) in a HID report.
old-location: hid\hidp_setusages.htm
tech.root: hid
ms.assetid: a9f229cd-33ca-42b5-bae6-3f367e5f1e84
ms.date: 04/30/2018
ms.keywords: HidP_SetUsages, HidP_SetUsages routine [Human Input Devices], hid.hidp_setusages, hidfunc_4d0213bb-2715-446b-bdaf-f82be3cbc11b.xml, hidpi/HidP_SetUsages
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Hidparse.lib
- Hidparse.dll
api_name:
- HidP_SetUsages
product:
- Windows
targetos: Windows
req.typenames: 
---

# HidP_SetUsages function


## -description


The <b>HidP_SetUsages</b> routine sets specified HID control buttons ON (1) in a HID report.


## -parameters




### -param ReportType [in]

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/ne-hidpi-_hidp_report_type">HIDP_REPORT_TYPE</a> enumerator value that indicates the type of report located at <i>Report</i>.


### -param UsagePage [in]

Specifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-usages">usage page</a> for the usages specified by <i>UsageList</i>.


### -param LinkCollection [in]

Specifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/link-collections">link collection</a> that contains the usages. If <i>LinkCollection</i> is nonzero, the routine only sets the usages, if they exist, in this link collection. If <i>LinkCollection</i> is zero, the routine sets the first usage for each specified usage in the <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection</a> associated with <i>PreparsedData</i>.


### -param UsageList [in, out]

Pointer to the array of usages.


### -param UsageLength [in, out]

Specifies, on input, the number of usages in <i>UsageList</i>. See the Remarks section for information about the output value.


### -param PreparsedData [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/preparsed-data">preparsed data</a> of the top-level collection associated with the report located at <i>Report</i>.


### -param Report [in]

Pointer to a report.


### -param ReportLength [in]

Specifies the size, in bytes, of the report located at <i>Report</i>, which must be equal to the report length for the specified report type that <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/nf-hidpi-hidp_getcaps">HidP_GetCaps</a> returns in a collection's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/ns-hidpi-_hidp_caps">HIDP_CAPS</a> structure.


## -returns



<b>HidP_SetUsages</b> returns one of the following status values:

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
<dt><b>HIDP_STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
A usage in a button array cannot be set because the array is already fully set.

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
A usage does not exist in the specified report, but it does exist in a different report of the specified type.

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
A usage does not exist in any report of the specified report type.

</td>
</tr>
</table>
 




## -remarks



If <b>HidP_SetUsages</b> cannot set a usage in <i>UsageList</i>, the routine sets <i>UsageLength</i> to the index of the usage that could not be set, and returns a status value that indicates the error.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hdpi-h-macros">HidP_GetButtons</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/nf-hidpi-hidp_getusages">HidP_GetUsages</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hdpi-h-macros">HidP_SetButtons</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hdpi-h-macros">HidP_UnsetButtons</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/nf-hidpi-hidp_unsetusages">HidP_UnsetUsages</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidsdi/nf-hidsdi-hidd_getpreparseddata">_HIDP_PREPARSED_DATA</a>
 

 

