---
UID: NF:hidpi.HidP_GetButtonCaps
title: HidP_GetButtonCaps function
author: windows-driver-content
description: The HidP_GetButtonCaps routine returns a button capability array that describes all the HID control buttons in a top-level collection for a specified type of HID report.
old-location: hid\hidp_getbuttoncaps.htm
old-project: hid
ms.assetid: 228b95b0-1087-422f-a995-809743c6103e
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: HidP_GetButtonCaps routine [Human Input Devices], HidP_GetButtonCaps, hid.hidp_getbuttoncaps, hidpi/HidP_GetButtonCaps, hidfunc_57425ae7-03dd-42b7-b9b3-0581569ab442.xml
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Hidparse.lib
-	Hidparse.dll
apiname:
-	HidP_GetButtonCaps
product: Windows
targetos: Windows
req.typenames: HIDP_REPORT_TYPE
---

# HidP_GetButtonCaps function


## -description


The <b>HidP_GetButtonCaps</b> routine returns a <a href="https://msdn.microsoft.com/139324e5-4d46-4d00-9f5a-fd0313fc109a">button capability array</a> that describes all the HID control buttons in a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> for a specified type of HID report.


## -syntax


````
NTSTATUS __stdcall HidP_GetButtonCaps(
  _In_    HIDP_REPORT_TYPE     ReportType,
  _Out_   PHIDP_BUTTON_CAPS    ButtonCaps,
  _Inout_ PUSHORT              ButtonCapsLength,
  _In_    PHIDP_PREPARSED_DATA PreparsedData
);
````


## -parameters




### -param ReportType [in]

Specifies a <a href="..\hidpi\ne-hidpi-_hidp_report_type.md">HIDP_REPORT_TYPE</a> enumerator value that identifies the report type.


### -param ButtonCaps [out]

Pointer to a caller-allocated buffer that the routine uses to return a button capability array for the specified report type.


### -param ButtonCapsLength [in, out]

Specifies the length on input, in array elements, of the buffer provided at <i>ButtonCaps</i>. On output, this parameter is set to the actual number of elements that the routine returns.


### -param PreparsedData [in]

Pointer to a top-level collection's <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a>.


## -returns


<b>HidP_GetButtonCaps</b> returns one of the following status values:
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
The routine successfully returned the capability data.

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


<b>HidP_GetButtonCaps</b> returns the capability of all buttons in a top level collection for a specified report type. 

<i>ButtonCapsLength</i> should be set to the value of the <b>Number</b><i>Xxx</i><b>ButtonCaps</b> member of the <a href="..\hidpi\ns-hidpi-_hidp_caps.md">HIDP_CAPS</a> structure returned by <a href="..\hidpi\nf-hidpi-hidp_getcaps.md">HidP_GetCaps</a>, where <i>Xxx</i> specifies the report type.

To obtain a subset of button capabilities, selected by <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage</a>, <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage page</a>, or <a href="https://msdn.microsoft.com/3f934661-c33c-4c08-82ac-ee2e0f519c8e">link collection</a>, use <a href="..\hidpi\nf-hidpi-hidp_getspecificbuttoncaps.md">HidP_GetSpecificButtonCaps</a>.

For more information about a collection's capability, see <a href="https://msdn.microsoft.com/0568993b-ff50-48ac-a875-95ab643d6c28">Obtaining Collection Information</a>.

See also <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 



## -see-also

<a href="..\hidpi\nf-hidpi-hidp_getspecificbuttoncaps.md">HidP_GetSpecificButtonCaps</a>

<a href="..\hidpi\ns-hidpi-_hidp_button_caps.md">HIDP_BUTTON_CAPS</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a>

<a href="..\hidpi\nf-hidpi-hidp_getcaps.md">HidP_GetCaps</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidP_GetButtonCaps routine%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

