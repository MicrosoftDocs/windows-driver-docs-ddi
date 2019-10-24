---
UID: NS:compstui._PROPSHEETUI_INFO
title: _PROPSHEETUI_INFO (compstui.h)
description: The PROPSHEETUI_INFO structure is used as an input parameter to PFNPROPSHEETUI-typed functions.
old-location: print\propsheetui_info.htm
tech.root: print
ms.assetid: b21c3ee1-13e8-4796-af45-6ba60e84df4e
ms.date: 04/20/2018
ms.keywords: "*PPROPSHEETUI_INFO, PPROPSHEETUI_INFO, PPROPSHEETUI_INFO structure pointer [Print Devices], PROPSHEETUI_INFO, PROPSHEETUI_INFO structure [Print Devices], _PROPSHEETUI_INFO, compstui/PPROPSHEETUI_INFO, compstui/PROPSHEETUI_INFO, cpsuifnc_0afe9ac8-ca1f-4984-acc5-04a8955b4b30.xml, print.propsheetui_info"
ms.topic: struct
f1_keywords:
 - "compstui/PROPSHEETUI_INFO"
req.header: compstui.h
req.include-header: Compstui.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- compstui.h
api_name:
- PROPSHEETUI_INFO
product:
- Windows
targetos: Windows
req.typenames: PROPSHEETUI_INFO, *PPROPSHEETUI_INFO
---

# _PROPSHEETUI_INFO structure


## -description


The PROPSHEETUI_INFO structure is used as an input parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui">PFNPROPSHEETUI</a>-typed functions.


## -struct-fields




### -field cbSize

CPSUI-supplied size, in bytes, of the PROPSHEETUI_INFO structure.


### -field Version

CPSUI-supplied version number of the PROPSHEETUI_INFO structure. The current version number is defined by PROPSHEETUI_INFO_VERSION in compstui.h.


### -field Flags

CPSUI-supplied bit flags. The following flag is defined:

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
PSUIINFO_UNICODE

</td>
<td>
If set, the calling application uses Unicode characters.

</td>
</tr>
</table>
 


### -field Reason

CPSUI-supplied constant specifying the action to be performed on the property sheet by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui">PFNPROPSHEETUI</a>-typed function to which the PROPSHEETUI_INFO structure was passed. One of the following constants will be supplied:

<ul>
<li>
PROPSHEETUI_REASON_DESTROY

</li>
<li>
PROPSHEETUI_REASON_GET_ICON

</li>
<li>
PROPSHEETUI_REASON_GET_INFO_HEADER

</li>
<li>
PROPSHEETUI_REASON_INIT

</li>
<li>
PROPSHEETUI_REASON_SET_RESULT

</li>
</ul>
For information about the meaning of each constant, see the Remarks section of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui">PFNPROPSHEETUI</a> description.


### -field hComPropSheet

CPSUI-supplied handle to a property sheet <a href="https://docs.microsoft.com/windows-hardware/drivers/print/group-parent">group parent</a>. This handle can be passed to CPSUI's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet">ComPropSheet</a> function.


### -field pfnComPropSheet

Address of CPSUI's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet">ComPropSheet</a> function.


### -field lParamInit

Value received as the <i>lParam</i> parameter for the associated PFNPROPSHEETUI-typed function, when the function was first called with a <b>Reason</b> of PROPSHEETUI_REASON_INIT. For information about what this value can be, see the description of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui">PFNPROPSHEETUI</a>.

This value is supplied by CPSUI, and is valid for all <b>Reason</b> values.


### -field UserData

Optional, private value or pointer supplied by the associated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui">PFNPROPSHEETUI</a>-typed function, initially set to zero by CPSUI. If the function stores a value in <b>UserData</b>, then for subsequent calls to the function, the stored value or pointer is unchanged unless changed by the function.


### -field Result

Result value supplied by the associated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui">PFNPROPSHEETUI</a>-typed function, initially set to zero by CPSUI. If the function stores a result value in <b>Result</b>, then for subsequent calls to the function, the stored value is unchanged unless changed by the function.

If the PFNPROPSHEETUI-typed function's address was specified as an argument to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nf-compstui-commonpropertysheetuia">CommonPropertySheetUI</a>, the last value stored in <b>Result</b> is returned to <b>CommonPropertySheetUI</b> in the location pointed to by its <i>pResult</i> argument.

