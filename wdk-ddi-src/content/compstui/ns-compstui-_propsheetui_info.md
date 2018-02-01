---
UID: NS:compstui._PROPSHEETUI_INFO
title: "_PROPSHEETUI_INFO"
author: windows-driver-content
description: The PROPSHEETUI_INFO structure is used as an input parameter to PFNPROPSHEETUI-typed functions.
old-location: print\propsheetui_info.htm
old-project: print
ms.assetid: b21c3ee1-13e8-4796-af45-6ba60e84df4e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*PPROPSHEETUI_INFO, PPROPSHEETUI_INFO structure pointer [Print Devices], compstui/PPROPSHEETUI_INFO, cpsuifnc_0afe9ac8-ca1f-4984-acc5-04a8955b4b30.xml, PPROPSHEETUI_INFO, PROPSHEETUI_INFO, compstui/PROPSHEETUI_INFO, _PROPSHEETUI_INFO, print.propsheetui_info, PROPSHEETUI_INFO structure [Print Devices]"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	compstui.h
apiname:
-	PROPSHEETUI_INFO
product: Windows
targetos: Windows
req.typenames: "*PPROPSHEETUI_INFO, PROPSHEETUI_INFO"
---

# _PROPSHEETUI_INFO structure


## -description


The PROPSHEETUI_INFO structure is used as an input parameter to <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a>-typed functions.


## -syntax


````
typedef struct _PROPSHEETUI_INFO {
  WORD            cbSize;
  WORD            Version;
  WORD            Flags;
  WORD            Reason;
  HANDLE          hComPropSheet;
  PFNCOMPROPSHEET pfnComPropSheet;
  LPARAM          lParamInit;
  ULONG_PTR       UserData;
  ULONG_PTR       Result;
} PROPSHEETUI_INFO, *PPROPSHEETUI_INFO;
````


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

CPSUI-supplied constant specifying the action to be performed on the property sheet by the <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a>-typed function to which the PROPSHEETUI_INFO structure was passed. One of the following constants will be supplied:
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
</ul>For information about the meaning of each constant, see the Remarks section of the <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a> description.


### -field hComPropSheet

CPSUI-supplied handle to a property sheet <a href="https://msdn.microsoft.com/b4c40c15-df16-4af0-81c8-9e70d26ba598">group parent</a>. This handle can be passed to CPSUI's <a href="https://msdn.microsoft.com/library/windows/hardware/ff546207">ComPropSheet</a> function.


### -field pfnComPropSheet

Address of CPSUI's <a href="https://msdn.microsoft.com/library/windows/hardware/ff546207">ComPropSheet</a> function.


### -field lParamInit

Value received as the <i>lParam</i> parameter for the associated PFNPROPSHEETUI-typed function, when the function was first called with a <b>Reason</b> of PROPSHEETUI_REASON_INIT. For information about what this value can be, see the description of <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a>.

This value is supplied by CPSUI, and is valid for all <b>Reason</b> values.


### -field UserData

Optional, private value or pointer supplied by the associated <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a>-typed function, initially set to zero by CPSUI. If the function stores a value in <b>UserData</b>, then for subsequent calls to the function, the stored value or pointer is unchanged unless changed by the function.


### -field Result

Result value supplied by the associated <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a>-typed function, initially set to zero by CPSUI. If the function stores a result value in <b>Result</b>, then for subsequent calls to the function, the stored value is unchanged unless changed by the function.

If the PFNPROPSHEETUI-typed function's address was specified as an argument to <a href="https://msdn.microsoft.com/library/windows/hardware/ff546148">CommonPropertySheetUI</a>, the last value stored in <b>Result</b> is returned to <b>CommonPropertySheetUI</b> in the location pointed to by its <i>pResult</i> argument.

