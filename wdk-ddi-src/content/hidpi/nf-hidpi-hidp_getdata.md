---
UID: NF:hidpi.HidP_GetData
title: HidP_GetData function
author: windows-driver-content
description: The HidP_GetData routine returns, for a specified report, an array of HIDP_DATA structures that identify the data indices of all HID control buttons that are currently set to ON (1), and the data indices and data associated with all HID control values.
old-location: hid\hidp_getdata.htm
old-project: hid
ms.assetid: 37cbd329-81c3-40ef-be42-4a64c4a1ec3a
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: hidpi/HidP_GetData, hidfunc_7d8a50f7-0ed4-4ba7-9ca4-70204c2a2699.xml, HidP_GetData, HidP_GetData routine [Human Input Devices], hid.hidp_getdata
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
-	HidP_GetData
product: Windows
targetos: Windows
req.typenames: HIDP_REPORT_TYPE
---

# HidP_GetData function


## -description


The <b>HidP_GetData</b> routine returns, for a specified report, an array of <a href="..\hidpi\ns-hidpi-_hidp_data.md">HIDP_DATA</a> structures that identify the <a href="https://msdn.microsoft.com/84577544-515a-4fdc-86e5-518182c6c461">data indices</a> of all HID control buttons that are currently set to ON (1), and the data indices and data associated with all HID control values.


## -syntax


````
NTSTATUS __stdcall HidP_GetData(
  _In_    HIDP_REPORT_TYPE     ReportType,
  _Out_   PHIDP_DATA           DataList,
  _Inout_ PULONG               DataLength,
  _In_    PHIDP_PREPARSED_DATA PreparsedData,
  _In_    PCHAR                Report,
  _In_    ULONG                ReportLength
);
````


## -parameters




### -param ReportType [in]

Specifies a <a href="..\hidpi\ne-hidpi-_hidp_report_type.md">HIDP_REPORT_TYPE</a> enumerator value that indicates the type of HID report located at <i>Report</i>.


### -param DataList [out]

Specifies a caller-allocated array of HIDP_DATA structures that the routine uses to return information about all the buttons that are currently set to ON and the data associated with values.


### -param DataLength [in, out]

Specifies, on input, the number of structures that the caller-allocated <i>DataList</i> array holds. Specifies, on output, the number of controls for which the routine can return data, which includes all buttons that are currently set to ON and all control values.


### -param PreparsedData [in]

Pointer to the <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a> of the top-level collection associated with the HID report located at <i>Report</i>.


### -param Report [in]

Pointer to a HID report.


### -param ReportLength [in]

Specifies the size, in bytes, of the HID report located at <i>Report</i>, which must be equal to the report length for the specified report type returned by <a href="..\hidpi\nf-hidpi-hidp_getcaps.md">HidP_GetCaps</a> in the collection's <a href="..\hidpi\ns-hidpi-_hidp_caps.md">HIDP_CAPS</a> structure.


## -returns


<b>HidP_GetData</b> returns one of the following status values:
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
All the control data was successfully returned.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INVALID_REPORT_TYPE</b></dt>
</dl>
</td>
<td width="60%">
The report type specified by <i>ReportType</i> is not valid

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INVALID_PREPARSED_DATA</b></dt>
</dl>
</td>
<td width="60%">
The preparsed data specified by <i>PreparsedData</i> is not valid

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INVALID_REPORT_LENGTH</b></dt>
</dl>
</td>
<td width="60%">
The size, in bytes, of the HID report is not equal to the length specified in the collection's <a href="..\hidpi\ns-hidpi-_hidp_caps.md">HIDP_CAPS</a> structure for the specified report type.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_REPORT_DOES_NOT_EXIST</b></dt>
</dl>
</td>
<td width="60%">
The top-level collection does not have a report of the specified type.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The <i>DataList</i> array is too small to describe all the buttons, currently set to ON, and all the values in the HID report.

</td>
</tr>
</table> 



## -remarks


User-mode applications and kernel-mode drivers call <a href="..\hidpi\nf-hidpi-hidp_maxdatalistlength.md">HidP_MaxDataListLength</a> to determine the maximum possible number of HIDP_DATA structures that <b>HidP_GetData</b> can return.

<b>HidP_GetData</b> does not return data for <a href="https://msdn.microsoft.com/d447dda6-a1e5-4e57-b06f-f79f8662c236">usage value arrays</a>.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 



## -see-also

<a href="..\hidpi\ns-hidpi-_hidp_data.md">HIDP_DATA</a>

<a href="..\hidpi\nf-hidpi-hidp_setdata.md">HidP_SetData</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a>

<a href="..\hidpi\nf-hidpi-hidp_maxdatalistlength.md">HidP_MaxDataListLength</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidP_GetData routine%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

