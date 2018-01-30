---
UID: NF:hidpi.HidP_GetValueCaps
title: HidP_GetValueCaps function
author: windows-driver-content
description: The HidP_GetValueCaps routine returns a value capability array that describes all the HID control values in a top-level collection for a specified type of HID report.
old-location: hid\hidp_getvaluecaps.htm
old-project: hid
ms.assetid: 74c26072-3b41-4d5c-96a1-d9c5b37ed97a
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: hid.hidp_getvaluecaps, HidP_GetValueCaps routine [Human Input Devices], hidpi/HidP_GetValueCaps, HidP_GetValueCaps, hidfunc_e600ab99-103c-43dd-b37b-fe35a96b2482.xml
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
-	HidP_GetValueCaps
product: Windows
targetos: Windows
req.typenames: HIDP_REPORT_TYPE
---

# HidP_GetValueCaps function


## -description


The <b>HidP_GetValueCaps</b> routine returns a <a href="https://msdn.microsoft.com/d447dda6-a1e5-4e57-b06f-f79f8662c236">value capability array</a> that describes all the HID control values in a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> for a specified type of HID report.


## -syntax


````
NTSTATUS __stdcall HidP_GetValueCaps(
  _In_    HIDP_REPORT_TYPE     ReportType,
  _Out_   PHIDP_VALUE_CAPS     ValueCaps,
  _Inout_ PUSHORT              ValueCapsLength,
  _In_    PHIDP_PREPARSED_DATA PreparsedData
);
````


## -parameters




### -param ReportType [in]

Specifies a <a href="..\hidpi\ne-hidpi-_hidp_report_type.md">HIDP_REPORT_TYPE</a> enumerator value that identifies the report type.


### -param ValueCaps [out]

Pointer to a caller-allocated buffer in which the routine returns a value capability array for the specified report type.


### -param ValueCapsLength [in, out]

Specifies the length, on input, in array elements, of the <i>ValueCaps </i>buffer. On output, the routine sets <i>ValueCapsLength</i> to the number of elements that the it actually returns.


### -param PreparsedData [in]

Pointer to a top-level collection's <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a>.


## -returns


<b>HidP_GetValueCaps</b> returns one of the following status values:
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


The correct length for <i>ValueCapsLength</i> is specified by the <b>Number</b><i>Xxx</i><b>ValueCaps </b>members of a top-level collection's <a href="..\hidpi\ns-hidpi-_hidp_caps.md">HIDP_CAPS</a> structure.

For more information about a collection's capability, see <a href="https://msdn.microsoft.com/0568993b-ff50-48ac-a875-95ab643d6c28">Obtaining Collection Information</a>.

See also <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 



## -see-also

<a href="..\hidpi\nf-hidpi-hidp_getcaps.md">HidP_GetCaps</a>

<a href="..\hidpi\ns-hidpi-_hidp_value_caps.md">HIDP_VALUE_CAPS</a>

<a href="..\hidpi\nf-hidpi-hidp_getvaluecaps.md">HidP_GetButtonCaps</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a>

<a href="..\hidpi\ns-hidpi-_hidp_caps.md">HIDP_CAPS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidP_GetValueCaps routine%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

