---
UID: NF:hidpi.HidP_GetUsageValue
title: HidP_GetUsageValue function
author: windows-driver-content
description: The HidP_GetUsageValue routine extracts the data associated with a HID control value that matches the selection criteria in a HID report.
old-location: hid\hidp_getusagevalue.htm
old-project: hid
ms.assetid: 5f2d1536-4676-4afe-aa5c-08e7c74d1dd2
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: hid.hidp_getusagevalue, hidfunc_d046d7e6-bd4c-4d80-80a8-f8e2d000eeee.xml, hidpi/HidP_GetUsageValue, HidP_GetUsageValue routine [Human Input Devices], HidP_GetUsageValue
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Hidparse.lib
-	Hidparse.dll
apiname:
-	HidP_GetUsageValue
product: Windows
targetos: Windows
req.typenames: HIDP_REPORT_TYPE
---

# HidP_GetUsageValue function


## -description


The <b>HidP_GetUsageValue</b> routine extracts the data associated with a HID control value that matches the selection criteria in a HID report.


## -syntax


````
NTSTATUS __stdcall HidP_GetUsageValue(
  _In_  HIDP_REPORT_TYPE     ReportType,
  _In_  USAGE                UsagePage,
  _In_  USHORT               LinkCollection,
  _In_  USAGE                Usage,
  _Out_ PULONG               UsageValue,
  _In_  PHIDP_PREPARSED_DATA PreparsedData,
  _In_  PCHAR                Report,
  _In_  ULONG                ReportLength
);
````


## -parameters




### -param ReportType [in]

Specifies a <a href="..\hidpi\ne-hidpi-_hidp_report_type.md">HIDP_REPORT_TYPE</a> enumerator value that identifies the report type.


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


<b>HidP_GetUsageValue</b> does not sign or scale the value. To extract a signed value, use <b>HidP_GetScaledUsageValue</b>. To manually assign the sign bit, the position of the sign bit can be determined from the information in a value's <a href="..\hidpi\ns-hidpi-_hidp_value_caps.md">HIDP_VALUE_CAPS</a> structure.

<b>HidP_GetUsageValue</b> is designed to extract a usage value for a usage whose report count is 1. If the specified usage has a report count greater than 1, the usage is part of a <a href="https://msdn.microsoft.com/d447dda6-a1e5-4e57-b06f-f79f8662c236">usage value array</a>. <b>HidP_GetUsageValue</b> only returns the first data item in a usage value array. To extract all data items in a usage value array, use <a href="..\hidpi\nf-hidpi-hidp_getusagevaluearray.md">HidP_GetUsageValueArray</a>. 

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539708">HidP_GetButtons</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539712">HidP_GetButtonsEx</a>

<a href="..\hidpi\nf-hidpi-hidp_getusages.md">HidP_GetUsages</a>

<a href="..\hidpi\ns-hidpi-_hidp_value_caps.md">HIDP_VALUE_CAPS</a>

<a href="..\hidpi\nf-hidpi-hidp_getusagevaluearray.md">HidP_GetUsageValueArray</a>

<a href="..\hidpi\nf-hidpi-hidp_getcaps.md">HidP_GetCaps</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a>

<a href="..\hidpi\nf-hidpi-hidp_getusagesex.md">HidP_GetUsagesEx</a>

<a href="..\hidpi\nf-hidpi-hidp_getscaledusagevalue.md">HidP_GetScaledUsageValue</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidP_GetUsageValue routine%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

