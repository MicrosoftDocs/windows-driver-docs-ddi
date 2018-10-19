---
UID: NS:compstui._PROPSHEETUI_INFO_HEADER
title: "_PROPSHEETUI_INFO_HEADER"
author: windows-driver-content
description: The PROPSHEETUI_INFO_HEADER structure is used as an input parameter to an application's PFNPROPSHEETUI-typed function, when the function is called with a reason value of PROPSHEETUI_REASON_GET_INFO_HEADER.
old-location: print\propsheetui_info_header.htm
tech.root: print
ms.assetid: 148c463c-a18b-4f24-b3dc-af74c3de97b7
ms.date: 04/20/2018
ms.keywords: "*PPROPSHEETUI_INFO_HEADER, PPROPSHEETUI_INFO_HEADER, PPROPSHEETUI_INFO_HEADER structure pointer [Print Devices], PROPSHEETUI_INFO_HEADER, PROPSHEETUI_INFO_HEADER structure [Print Devices], _PROPSHEETUI_INFO_HEADER, compstui/PPROPSHEETUI_INFO_HEADER, compstui/PROPSHEETUI_INFO_HEADER, cpsuifnc_21dad179-56e1-478c-8a62-628262ca59a8.xml, print.propsheetui_info_header"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	compstui.h
api_name:
-	PROPSHEETUI_INFO_HEADER
product:
- Windows
targetos: Windows
req.typenames: PROPSHEETUI_INFO_HEADER, *PPROPSHEETUI_INFO_HEADER
---

# _PROPSHEETUI_INFO_HEADER structure


## -description


The PROPSHEETUI_INFO_HEADER structure is used as an input parameter to an application's <a href="https://msdn.microsoft.com/library/windows/hardware/ff559812">PFNPROPSHEETUI</a>-typed function, when the function is called with a reason value of PROPSHEETUI_REASON_GET_INFO_HEADER.


## -struct-fields




### -field cbSize

CPSUI-supplied size, in bytes, of the PROPSHEETUI_INFO_HEADER structure.


### -field Flags

Optional, application-specified bit flags that modify the property sheet page's appearance. The flags listed in the following table can be used in any combination.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
PSUIHDRF_DEFTITLE

</td>
<td>
If set, CPSUI should include "Default" in the title bar string. CPSUI adds "Default" after the <b>pTitle</b> string and, if PSUIHDRF_PROPTITLE is set, before "Properties".

</td>
</tr>
<tr>
<td>
PSUIHDRF_EXACT_PTITLE

</td>
<td>
If set, CPSUI uses the text specified by <b>pTitle</b> without modification. This flag overrides PSUIHDRF_DEFTITLE and PSUIHDRF_PROPTITLE.

</td>
</tr>
<tr>
<td>
PSUIHDRF_NOAPPLYNOW

</td>
<td>
If set, CPSUI should not include an <b>Apply Now</b> button.

</td>
</tr>
<tr>
<td>
PSUIHDRF_PROPTITLE

</td>
<td>
If set, CPSUI should append "Properties" to the title bar string. (By default, CPSUI sets this flag before calling the application.)

</td>
</tr>
<tr>
<td>
PSUIHDRF_USEHICON

</td>
<td>
If set, the <b>hIcon</b>/<b>IconID</b> union contains an icon handle. If not set, the union contains an icon resource identifier.

</td>
</tr>
</table>
 


### -field pTitle

String identifier, representing text to be displayed in the property sheet's title bar. This can be a 32-bit pointer to a NULL-terminated string, or it can be a 16-bit string resource identifier with HIWORD set to zero. For printer interface DLLs, the string typically contains the printer's name.


### -field hWndParent

Handle to the window to be used as the parent of the property sheet. By default, CPSUI supplies the window handle that it received for the <i>hWndOwner</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff546148">CommonPropertySheetUI</a>, but the application can overwrite that handle with another.


### -field hInst

Application-supplied instance handle, which CPSUI uses when loading application resources.


### -field DUMMYUNIONNAME

 


### -field DUMMYUNIONNAME.hIcon


### -field DUMMYUNIONNAME.IconID

This union identifies the icon to be displayed in the property sheet's title bar. The union member is selected by PSUIHDRF_USEICON in <b>Flags</b>.

