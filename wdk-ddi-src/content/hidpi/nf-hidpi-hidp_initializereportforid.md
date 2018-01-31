---
UID: NF:hidpi.HidP_InitializeReportForID
title: HidP_InitializeReportForID function
author: windows-driver-content
description: The HidP_InitializeReportForID routine initializes a HID report.
old-location: hid\hidp_initializereportforid.htm
old-project: hid
ms.assetid: 9d56a07e-8898-4bd6-93ae-752ff7d3b215
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: hidpi/HidP_InitializeReportForID, hidfunc_b02350cf-7d33-4a71-9afb-4b3c07e52650.xml, HidP_InitializeReportForID, HidP_InitializeReportForID routine [Human Input Devices], hid.hidp_initializereportforid
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
-	HidP_InitializeReportForID
product: Windows
targetos: Windows
req.typenames: HIDP_REPORT_TYPE
---

# HidP_InitializeReportForID function


## -description


The <b>HidP_InitializeReportForID</b> routine initializes a HID report.


## -syntax


````
NTSTATUS __stdcall HidP_InitializeReportForID(
  _In_  HIDP_REPORT_TYPE     ReportType,
  _In_  UCHAR                ReportID,
  _In_  PHIDP_PREPARSED_DATA PreparsedData,
  _Out_ PCHAR                Report,
  _In_  ULONG                ReportLength
);
````


## -parameters




#### - ReportType [in]

Specifies a <a href="..\hidpi\ne-hidpi-_hidp_report_type.md">HIDP_REPORT_TYPE</a> enumerator that indicates the type of HID report located at <i>Report</i>.


#### - ReportID [in]

Specifies a report ID.


#### - PreparsedData [in]

Pointer to the <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a> of the <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> associated with the HID report located at <i>Report</i>.


#### - Report [out]

Pointer to the caller-allocated buffer containing the HID report that <b>HidP_InitializeReportForID</b> initializes.


#### - ReportLength [in]

Specifies the size, in bytes, of the HID report located at <i>Report</i>. <i>ReportLength</i> must be equal to the collection's report length for the specified report type, as specified by the <i>Xxx</i><b>ReportByteLength</b> members of a collection's <a href="..\hidpi\ns-hidpi-_hidp_caps.md">HIDP_CAPS</a> structure.


## -returns


<b>HidP_InitializeReportForID</b> returns one of the following status values:
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
The report was successfully initialized.

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
<dt><b>HIDP_STATUS_INVALID_REPORT_LENGTH</b></dt>
</dl>
</td>
<td width="60%">
The specified length of the report is not equal to the collection's report length for the specified report type. 

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
The specified report ID is not valid.

</td>
</tr>
</table> 



## -remarks


Initializing a HID report sets all control data to zero or a control's <i>null value</i>, as defined by the USB HID standard. (Sending or receiving a null value indicates that the current value of a control should not be modified.)

<b>HidP_InitializeReportForID</b> does the following:
<ul>
<li>
Sets to zero the bitfields of all buttons and values without null values.

</li>
<li>
Sets the bitfield of all controls with null values to their corresponding null value.

</li>
</ul>For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 



## -see-also

<a href="..\hidpi\ns-hidpi-_hidp_caps.md">HIDP_CAPS</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a>

<a href="..\hidpi\ne-hidpi-_hidp_report_type.md">HIDP_REPORT_TYPE</a>

<a href="..\hidpi\nf-hidpi-hidp_getcaps.md">HidP_GetCaps</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidP_InitializeReportForID routine%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

