---
UID: NF:hidpi.HidP_GetUsages
title: HidP_GetUsages function
author: windows-driver-content
description: The HidP_GetUsages routine returns a list of all the HID control button usages that are on a specified usage page and are set to ON in a HID report.
old-location: hid\hidp_getusages.htm
old-project: hid
ms.assetid: e35ae7c6-2cf4-4f20-bb00-7f33ae133118
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: HidP_GetUsages
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
req.alt-api: HidP_GetUsages
req.alt-loc: Hidparse.lib,Hidparse.dll
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
req.typenames: HIDP_REPORT_TYPE
---

# HidP_GetUsages function



## -description
The <b>HidP_GetUsages </b>routine returns a list of all the HID control button <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usages</a> that are on a specified <a href="hid.hid_usages#usage_page#usage_page">usage page</a> and are set to ON in a HID report. 



## -syntax

````
NTSTATUS __stdcall HidP_GetUsages(
  _In_    HIDP_REPORT_TYPE     ReportType,
  _In_    USAGE                UsagePage,
  _In_    USHORT               LinkCollection,
  _Out_   PUSAGE               UsageList,
  _Inout_ PULONG               UsageLength,
  _In_    PHIDP_PREPARSED_DATA PreparsedData,
  _Out_   PCHAR                Report,
  _In_    ULONG                ReportLength
);
````


## -parameters

### -param ReportType [in]

Specifies a <a href="..\hidpi\ne-hidpi-_hidp_report_type.md">HIDP_REPORT_TYPE</a> enumerator value that identifies the report type.


### -param UsagePage [in]

Specifies the <a href="hid.hid_usages#usage_page#usage_page">usage page</a> of the button usages. The routine only returns information about buttons on this usage page.


### -param LinkCollection [in]

Specifies the <a href="https://msdn.microsoft.com/3f934661-c33c-4c08-82ac-ee2e0f519c8e">link collection</a> of the button usages. If <i>LinkCollection</i> is nonzero, the routine only returns information about the buttons that this link collection contains; otherwise, if <i>LinkCollection</i> is zero, the routine returns information about all the buttons in the <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> associated with <i>PreparsedData</i>.


### -param UsageList [out]

Pointer to a caller-allocated buffer that the routine uses to return the usages of all buttons that are set to ON and belong to the usage page specified by <i>UsagePage</i>. 


### -param UsageLength [in, out]

Specifies, on input, the length, in array elements, of the <i>UsageList</i> buffer. Specifies, on output, the number of buttons that are set to ON on the specified usage page.


### -param PreparsedData [in]

Pointer to a top-level collection's <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a>.


### -param Report [out]

Pointer to a report.


### -param ReportLength [in]

Specifies the length, in bytes, of the report located at <i>Report</i>.


## -returns
<b>HidP_GetUsages</b> returns one of the following status values:
<dl>
<dt><b>HIDP_STATUS_SUCCESS</b></dt>
</dl>The routine successfully returned all button usages set to ON.
<dl>
<dt><b>HIDP_INVALID_REPORT_LENGTH</b></dt>
</dl>The report length is not valid.
<dl>
<dt><b>HIDP_INVALID_REPORT_TYPE</b></dt>
</dl>The specified report type is not valid.
<dl>
<dt><b>HIDP_STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The <i>UsageList</i> buffer is too small to hold all the usages that are currently set to ON on the specified usage page.
<dl>
<dt><b>HIDP_STATUS_INCOMPATIBLE_REPORT_ID</b></dt>
</dl>The collection contains buttons on the specified usage page in a report of the specified type, but there are no such usages in the specified report.
<dl>
<dt><b>HIDP_STATUS_INVALID_PREPARSED_DATA</b></dt>
</dl>The preparsed data is not valid.
<dl>
<dt><b>HIDP_STATUS_USAGE_NOT_FOUND</b></dt>
</dl>The collection does not contain any buttons on the specified usage page in any report of the specified report type.

 


## -remarks
User-mode applications and kernel-mode drivers call <a href="..\hidpi\nf-hidpi-hidp_maxusagelistlength.md">HidP_MaxUsageListLength</a> to determine the maximum number of buttons that can be returned for specified report type. Alternatively, applications or drivers can call <b>HidP_GetUsages</b> and set <i>UsageList </i>to zero to return the required length in <i>UsageLength</i>.

Applications or drivers determine the required report length from the <i>Xxx</i><b>ReportByteLength</b> members in a top-level collection's <a href="..\hidpi\ns-hidpi-_hidp_caps.md">HIDP_CAPS</a> structure.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539708">HidP_GetButtons</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539712">HidP_GetButtonsEx</a>
</dt>
<dt>
<a href="..\hidpi\nf-hidpi-hidp_getcaps.md">HidP_GetCaps</a>
</dt>
<dt>
<a href="..\hidpi\nf-hidpi-hidp_getscaledusagevalue.md">HidP_GetScaledUsageValue</a>
</dt>
<dt>
<a href="..\hidpi\nf-hidpi-hidp_getusagesex.md">HidP_GetUsagesEx</a>
</dt>
<dt>
<a href="..\hidpi\nf-hidpi-hidp_getusagevalue.md">HidP_GetUsageValue</a>
</dt>
<dt>
<a href="..\hidpi\nf-hidpi-hidp_getusagevaluearray.md">HidP_GetUsageValueArray</a>
</dt>
<dt>
<a href="..\hidpi\nf-hidpi-hidp_maxusagelistlength.md">HidP_MaxUsageListLength</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidP_GetUsages routine%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

