---
UID: NF:hidpi.HidP_GetUsagesEx
title: HidP_GetUsagesEx function
author: windows-driver-content
description: The HidP_GetUsagesEx routine returns a list of the all the HID control button usages that are set to ON in a HID report.
old-location: hid\hidp_getusagesex.htm
old-project: hid
ms.assetid: c799ecb6-3024-491c-90d5-70e1d21b1baf
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: HidP_GetUsagesEx, HidP_GetUsagesEx routine [Human Input Devices], hid.hidp_getusagesex, hidfunc_2a2a6e4a-c966-43d7-8159-115bb6f2376c.xml, hidpi/HidP_GetUsagesEx
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
-	HidP_GetUsagesEx
product: Windows
targetos: Windows
req.typenames: HIDP_REPORT_TYPE
---

# HidP_GetUsagesEx function


## -description


The <b>HidP_GetUsagesEx</b> routine returns a list of the all the HID control button <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usages</a> that are set to ON in a HID report. 


## -parameters




### -param ReportType [in]

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539774">HIDP_REPORT_TYPE</a> enumerator value that identifies the report type.


### -param LinkCollection [in]

Specifies the <a href="https://msdn.microsoft.com/3f934661-c33c-4c08-82ac-ee2e0f519c8e">link collection</a> of the button usages. If <i>LinkCollection</i> is nonzero, the routine only returns information about the buttons that this link collection contains; otherwise, if <i>LinkCollection</i> is zero, the routine returns information about all the buttons in the <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> associated with <i>PreparsedData</i>.


### -param ButtonList [in, out]

Pointer to a caller-allocated buffer that routine uses to return the usage and <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage page</a> identifiers for each button that is set to ON (1).


### -param UsageLength [in, out]

Specifies, on input, the length, in array elements, of the <i>ButtonList</i> buffer. Specifies, on output, the number usages that are currently set to ON in the specified report.


### -param PreparsedData [in]

Pointer to a top-level collection's <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a>.


### -param Report [in]

Pointer to a report that contains button data.


### -param ReportLength [in]

Specifies the length, in bytes, of the report located at <i>Report</i>.


## -returns



<b>HidP_GetUsagesEx</b> returns one of the following status values:

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
The <i>UsageList</i> buffer is too small to hold all the usages currently set to ON in the specified report.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INCOMPATIBLE_REPORT_ID</b></dt>
</dl>
</td>
<td width="60%">
The collection contains buttons in a report of the specified type, but there are no such usages in the specified report.

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
</table>
 




## -remarks



User-mode applications and kernel-mode drivers call <a href="https://msdn.microsoft.com/library/windows/hardware/ff539770">HidP_MaxUsageListLength</a> to determine the maximum number of buttons that be returned for specified report type. Alternatively, applications or drivers can call <b>HidP_GetUsagesEx</b> and set <i>UsageList </i>to zero to return the required length in <i>UsageLength</i>.

Applications or drivers determine the required report length from the <i>Xxx</i><b>ReportByteLength</b> members in a top-level collection's <a href="https://msdn.microsoft.com/library/windows/hardware/ff539697">HIDP_CAPS</a> structure.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539708">HidP_GetButtons</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539712">HidP_GetButtonsEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539715">HidP_GetCaps</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539729">HidP_GetScaledUsageValue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539748">HidP_GetUsageValue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539750">HidP_GetUsageValueArray</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539745">HidP_GetUsagesEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539770">HidP_MaxUsageListLength</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543483">USAGE_AND_PAGE</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a>
 

 

