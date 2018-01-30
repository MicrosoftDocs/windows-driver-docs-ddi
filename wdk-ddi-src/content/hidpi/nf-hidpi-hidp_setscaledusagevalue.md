---
UID: NF:hidpi.HidP_SetScaledUsageValue
title: HidP_SetScaledUsageValue function
author: windows-driver-content
description: The HidP_SetScaledUsageValue routine converts a signed and scaled physical number to a HID usage's logical value, and sets the usage value in a specified HID report.
old-location: hid\hidp_setscaledusagevalue.htm
old-project: hid
ms.assetid: 0b863b69-b736-49dd-94a9-283480d035be
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: HidP_SetScaledUsageValue, hidpi/HidP_SetScaledUsageValue, hid.hidp_setscaledusagevalue, hidfunc_0fcd2d78-aae7-4d56-a930-9bf0e4a417bf.xml, HidP_SetScaledUsageValue routine [Human Input Devices]
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
-	HidP_SetScaledUsageValue
product: Windows
targetos: Windows
req.typenames: HIDP_REPORT_TYPE
---

# HidP_SetScaledUsageValue function


## -description


The <b>HidP_SetScaledUsageValue</b> routine converts a signed and scaled physical number to a <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">HID usage's</a> logical value, and sets the usage value in a specified HID report.


## -syntax


````
NTSTATUS __stdcall HidP_SetScaledUsageValue(
  _In_    HIDP_REPORT_TYPE     ReportType,
  _In_    USAGE                UsagePage,
  _In_    USHORT               LinkCollection,
  _In_    USAGE                Usage,
  _In_    LONG                 UsageValue,
  _In_    PHIDP_PREPARSED_DATA PreparsedData,
  _Inout_ PCHAR                Report,
  _In_    ULONG                ReportLength
);
````


## -parameters




### -param ReportType [in]

Specifies a <a href="..\hidpi\ne-hidpi-_hidp_report_type.md">HIDP_REPORT_TYPE</a> enumerator value that indicates the type of HID report located at <i>Report</i>.


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

Specifies the size, in bytes, of the HID report located at <i>Report</i>, which must be equal to the report length for the specified report type that <a href="..\hidpi\nf-hidpi-hidp_getcaps.md">HidP_GetCaps</a> returns in a collection's <a href="..\hidpi\ns-hidpi-_hidp_caps.md">HIDP_CAPS</a> structure.


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

<a href="..\hidpi\nf-hidpi-hidp_setusagevalue.md">HidP_SetUsageValue</a>

<a href="..\hidpi\nf-hidpi-hidp_getcaps.md">HidP_GetCaps</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a>

<a href="..\hidpi\nf-hidpi-hidp_setusagevaluearray.md">HidP_SetUsageValueArray</a>

<a href="..\hidpi\ne-hidpi-_hidp_report_type.md">HIDP_REPORT_TYPE</a>

<a href="..\hidpi\ns-hidpi-_hidp_caps.md">HIDP_CAPS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidP_SetScaledUsageValue routine%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

