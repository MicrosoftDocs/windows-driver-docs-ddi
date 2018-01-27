---
UID: NF:hidpi.HidP_GetSpecificButtonCaps
title: HidP_GetSpecificButtonCaps function
author: windows-driver-content
description: The HidP_GetSpecificButtonCaps routine returns a button capability array that describes all HID control buttons in a top-level collection that meet a specified selection criteria.
old-location: hid\hidp_getspecificbuttoncaps.htm
old-project: hid
ms.assetid: 923693a2-cb46-4f74-bb1b-cd7bb07014e8
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: HidP_GetSpecificButtonCaps, HidP_GetSpecificButtonCaps routine [Human Input Devices], hidpi/HidP_GetSpecificButtonCaps, hidfunc_dd31da1d-fb42-4ac9-a15e-4c6585785c20.xml, hid.hidp_getspecificbuttoncaps
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
-	HidP_GetSpecificButtonCaps
product: Windows
targetos: Windows
req.typenames: HIDP_REPORT_TYPE
---

# HidP_GetSpecificButtonCaps function


## -description


The <b>HidP_GetSpecificButtonCaps</b> routine returns a <a href="https://msdn.microsoft.com/139324e5-4d46-4d00-9f5a-fd0313fc109a">button capability array</a> that describes all HID control buttons in a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> that meet a specified selection criteria.


## -syntax


````
NTSTATUS __stdcall HidP_GetSpecificButtonCaps(
  _In_    HIDP_REPORT_TYPE     ReportType,
  _In_    USAGE                UsagePage,
  _In_    USHORT               LinkCollection,
  _In_    USAGE                Usage,
  _Out_   PHIDP_BUTTON_CAPS    ButtonCaps,
  _Inout_ PUSHORT              ButtonCapsLength,
  _In_    PHIDP_PREPARSED_DATA PreparsedData
);
````


## -parameters




### -param ReportType [in]

Specifies a <a href="..\hidpi\ne-hidpi-_hidp_report_type.md">HIDP_REPORT_TYPE</a> enumerator value that identifies the report type.


### -param UsagePage [in]

Specifies a usage page as a search criteria. If <i>UsagePage</i> is nonzero, only buttons that specify this usage page are returned.


### -param LinkCollection [in]

Specifies a <a href="https://msdn.microsoft.com/3f934661-c33c-4c08-82ac-ee2e0f519c8e">link collection</a> as a search criteria. If <i>LinkCollection</i> is nonzero, only buttons that are part of this link collection are returned.


### -param Usage [in]

Specifies a <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">HID usage</a> as a search criteria. If <i>Usage</i> is nonzero, only buttons that specify this usage will be returned.


### -param ButtonCaps [out]

Pointer to a caller-allocated buffer in which the routine returns a button capability array for the specified report type.


### -param ButtonCapsLength [in, out]

Specifies the length on input, in array elements, of the buffer provided at <i>ButtonCaps</i>. On output, this parameter is set to the number of elements that the routine actually returned.


### -param PreparsedData [in]

Pointer to a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection's</a> <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a>.


## -returns


<b>HidP_GetSpecificButtonCaps</b> returns one of the following status values:
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


The required size of the <i>ButtonCaps</i> array is specified by the <b>Number</b><i>Xxx</i><b>ButtonCaps </b>members of a top-level collection's <a href="..\hidpi\ns-hidpi-_hidp_caps.md">HIDP_CAPS</a> structure.

When calling <b>HidP_GetSpecificButtonCaps</b>, specifying zero for <i>UsagePage</i>, <i>Usage</i>, and <i>LinkCollection</i> is equivalent to calling <b>HidP_GetButtonCaps</b>.

For more information about a collection's capability, see <a href="https://msdn.microsoft.com/0568993b-ff50-48ac-a875-95ab643d6c28">Obtaining Collection Information</a>.

See also <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 



## -see-also

<a href="..\hidpi\nf-hidpi-hidp_getcaps.md">HidP_GetCaps</a>

<a href="..\hidpi\ns-hidpi-_hidp_button_caps.md">HIDP_BUTTON_CAPS</a>

<a href="..\hidpi\nf-hidpi-hidp_getbuttoncaps.md">HidP_GetButtonCaps</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidP_GetSpecificButtonCaps routine%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

