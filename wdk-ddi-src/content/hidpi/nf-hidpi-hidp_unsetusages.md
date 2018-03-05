---
UID: NF:hidpi.HidP_UnsetUsages
title: HidP_UnsetUsages function
author: windows-driver-content
description: The HidP_UnsetUsages routine sets specified HID control button usages OFF (zero) in a HID report.
old-location: hid\hidp_unsetusages.htm
old-project: hid
ms.assetid: 55dcd9f3-6903-4718-98c2-ee42ee1026e3
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: HidP_UnsetUsages, HidP_UnsetUsages routine [Human Input Devices], hid.hidp_unsetusages, hidfunc_7ffa6677-1a45-4e19-8001-116fbeacf097.xml, hidpi/HidP_UnsetUsages
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Hidparse.lib
-	Hidparse.dll
api_name:
-	HidP_UnsetUsages
product: Windows
targetos: Windows
req.typenames: HIDP_REPORT_TYPE
---

# HidP_UnsetUsages function


## -description


The <b>HidP_UnsetUsages</b> routine sets specified HID control button <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usages</a> OFF (zero) in a HID report.


## -syntax


````
NTSTATUS __stdcall HidP_UnsetUsages(
  _In_     HIDP_REPORT_TYPE     ReportType,
  _In_     USAGE                UsagePage,
  _In_opt_ USHORT               LinkCollection,
  _Inout_  PUSAGE               UsageList,
  _Inout_  PULONG               UsageLength,
  _In_     PHIDP_PREPARSED_DATA PreparsedData,
  _In_     PCHAR                Report,
  _In_     ULONG                ReportLength
);
````


## -parameters




### -param ReportType [in]

Specifies a <a href="..\hidpi\ne-hidpi-_hidp_report_type.md">HIDP_REPORT_TYPE</a> enumerator value that indicates the type of report located at <i>Report</i>.


### -param UsagePage [in]

Specifies the usage page of the usages specified by <i>UsageList</i>.


### -param LinkCollection [in, optional]

Specifies the <a href="https://msdn.microsoft.com/3f934661-c33c-4c08-82ac-ee2e0f519c8e">link collection</a> that contains the usages. If <i>LinkCollection</i> is nonzero, the routine only sets the usages, if they exist, in this link collection. If <i>LinkCollection</i> is zero, the routine sets the first usage for each usage it finds in the <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> associated with <i>PreparsedData</i>.


### -param UsageList [in, out]

Pointer to the array of usages to set to OFF.


### -param UsageLength [in, out]

Specifies, on input, the number of usages in <i>UsageList</i>. See the Remarks section for information about the output value.


### -param PreparsedData [in]

Pointer to the <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a> of the top-level collection associated with the report located at <i>Report</i>.


### -param Report [in]

Pointer to a report.


### -param ReportLength [in]

Specifies the size, in bytes, of the report located at <i>Report</i>, which must be equal to the report length for the specified report type that <a href="..\hidclass\nc-hidclass-phidp_getcaps.md">HidP_GetCaps</a> returns in a collection's <a href="..\hidpi\ns-hidpi-_hidp_caps.md">HIDP_CAPS</a> structure.


## -returns



<b>HidP_UnsetUsages</b> returns HIDP_STATUS_SUCCESS if it successfully sets to OFF all the usages in <i>UsageList</i>.

<b>HidP_UnsetUsages </b>returns one of the following status values if one of the input parameters is not valid:

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
The report type is not valid.

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
 

<b>HidP_UnsetUsages</b> returns one of the following status values if it was not able to set to OFF one of the usages in <i>UsageList</i>:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_BUTTON_NOT_PRESSED</b></dt>
</dl>
</td>
<td width="60%">

A usage is already set to OFF.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INCOMPATIBLE_REPORT_ID</b></dt>
</dl>
</td>
<td width="60%">

A usage is not contained in the specified report, but is contained in another report of the specified type.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_USAGE_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">


The routine did not find a usage in any report of the specified type.

</td>
</tr>
</table>
 




## -remarks



<b>HidP_UnsetUsages</b> sets <i>UsageLength</i> as follows:



For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 




## -see-also

<a href="..\hidpi\nf-hidpi-hidp_setdata.md">HidP_SetData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539779">HidP_SetButtons</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a>



<a href="..\hidpi\nf-hidpi-hidp_setusages.md">HidP_SetUsages</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539812">HidP_UnsetButtons</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidP_UnsetUsages routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

