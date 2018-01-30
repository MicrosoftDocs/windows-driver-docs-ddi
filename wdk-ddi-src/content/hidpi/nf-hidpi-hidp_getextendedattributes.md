---
UID: NF:hidpi.HidP_GetExtendedAttributes
title: HidP_GetExtendedAttributes function
author: windows-driver-content
description: The HidP_GetExtendedAttributes routine returns the extended attributes of a HID control.
old-location: hid\hidp_getextendedattributes.htm
old-project: hid
ms.assetid: 97a8822f-ed0c-43ae-8b4e-08642558773d
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: HidP_GetExtendedAttributes, HidP_GetExtendedAttributes routine [Human Input Devices], hid.hidp_getextendedattributes, hidpi/HidP_GetExtendedAttributes, hidfunc_2870ef44-8659-4c02-9fc6-659581684253.xml
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
req.irql: "<= DISPATCH_ LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Hidparse.lib
-	Hidparse.dll
apiname:
-	HidP_GetExtendedAttributes
product: Windows
targetos: Windows
req.typenames: HIDP_REPORT_TYPE
---

# HidP_GetExtendedAttributes function


## -description


The <b>HidP_GetExtendedAttributes</b> routine returns the extended attributes of a HID control.


## -syntax


````
NTSTATUS __stdcall HidP_GetExtendedAttributes(
  _In_    HIDP_REPORT_TYPE          ReportType,
  _In_    USHORT                    DataIndex,
  _In_    PHIDP_PREPARSED_DATA      PreparsedData,
  _Out_   PHIDP_EXTENDED_ATTRIBUTES Attributes,
  _Inout_ PULONG                    LengthAttributes
);
````


## -parameters




### -param ReportType [in]

Specifies a <a href="..\hidpi\ne-hidpi-_hidp_report_type.md">HIDP_REPORT_TYPE</a> enumerator value that indicates the type of HID report associated with the HID control specified by <i>DataIndex</i>.


### -param DataIndex [in]

Specifies the <a href="https://msdn.microsoft.com/84577544-515a-4fdc-86e5-518182c6c461">data index</a> of the HID control.


### -param PreparsedData [in]

Specifies the <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a> for the <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> that contains the specified control.


### -param Attributes [out]

Pointer to a caller-allocated buffer that the routine uses to return the extended attributes of the control specified by <i>DataIndex</i>.


### -param LengthAttributes [in, out]

Specifies the size, in bytes, of the <i>Attributes</i> buffer (which must be greater than or equal to sizeof(HIDP_EXTENDED_ATTRIBUTES).


## -returns


<b>HidP_GetExtendedAttributes</b> returns one of the following status values:
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
The routine successfully returned all the control's extended attribute information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The <i>Attribute</i> buffer was not large enough to hold all the extended attribute information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_DATA_INDEX_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The specified data index is not valid.

</td>
</tr>
</table> 



## -remarks


<b>HidP_GetExtendedAttributes </b>returns a variable length <a href="..\hidpi\ns-hidpi-_hidp_extended_attributes.md">HIDP_EXTENDED_ATTRIBUTES</a> structure in the <i>Attribute</i> buffer. The extended attributes structure contains, in consecutive order, the fixed length members (<b>NumGlobalUnknowns</b>, <b>Reserved</b>, and <b>GlobalUnknowns</b>) followed by a variable length array of <a href="..\hidpi\ns-hidpi-_hidp_unknown_token.md">HIDP_UNKNOWN_TOKEN</a> structures. The first member of the unknown token array is located at (PHIDP_UNKNOWN_TOKEN*)&amp;(<i>Attributes</i>-&gt;<b>Data</b>).

The routine returns as many bytes of the extended attribute information as the <i>Attribute</i> buffer can hold. If the buffer is too small, the routine truncates the information it returns. To determine the number of unknown tokens in the variable length array, a caller can first use the <i>Attributes</i> buffer to return the value of the <b>NumGlobalUnknowns</b> member of the extended attributes information.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 



## -see-also

<a href="..\hidpi\ns-hidpi-_hidp_unknown_token.md">HIDP_UNKNOWN_TOKEN</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a>

<a href="..\hidpi\ns-hidpi-_hidp_extended_attributes.md">HIDP_EXTENDED_ATTRIBUTES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidP_GetExtendedAttributes routine%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

