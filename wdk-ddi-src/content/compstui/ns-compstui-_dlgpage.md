---
UID: NS:compstui._DLGPAGE
title: "_DLGPAGE"
author: windows-driver-content
description: The DLGPAGE structure is used for specifying a property sheet page to CPSUI's ComPropSheet function. The structure's address is included in a COMPROPSHEETUI structure, and all member values are supplied by the ComPropSheet caller.
old-location: print\dlgpage.htm
old-project: print
ms.assetid: 61fb66b9-afd7-4ec4-bbbb-66a287398484
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDLGPAGE, DLGPAGE, DLGPAGE structure [Print Devices], PDLGPAGE, PDLGPAGE structure pointer [Print Devices], _DLGPAGE, compstui/DLGPAGE, compstui/PDLGPAGE, cpsuifnc_5054b61d-a4fc-4017-a491-4d753ce3e137.xml, print.dlgpage"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	compstui.h
api_name:
-	DLGPAGE
product: Windows
targetos: Windows
req.typenames: DLGPAGE, *PDLGPAGE
---

# _DLGPAGE structure


## -description


The DLGPAGE structure is used for specifying a property sheet page to CPSUI's <a href="https://msdn.microsoft.com/library/windows/hardware/ff546207">ComPropSheet</a> function. The structure's address is included in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546211">COMPROPSHEETUI</a> structure, and all member values are supplied by the <b>ComPropSheet</b> caller.


## -struct-fields




### -field cbSize

Caller-supplied size, in bytes, of the DLGPAGE structure.


### -field Flags

Caller-supplied bit flags, as described in the following table.

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
DPF_ICONID_AS_HICON

</td>
<td>
If set, IconID contains an icon handle.

If not set, IconID contains an icon resource identifier.

</td>
</tr>
<tr>
<td>
DPF_USE_HDLGTEMPLATE

</td>
<td>
If set, <b>hDlgTemplate</b> contains a template handle.

If not set, <b>DlgTemplateID</b> contains a template resource identifier.

</td>
</tr>
</table>
 


### -field DlgProc

Optional, caller-supplied DLGPROC-typed pointer to a dialog box procedure, used to process messages sent by the system when user events occur. (The DLGPROC pointer type is described in the Microsoft Windows SDK documentation.) If <b>NULL</b>, CPSUI supplies a dialog box procedure. For more information, see the following Remarks section.


### -field pTabName

Caller-supplied pointer to a NULL-terminated string to be displayed on the page tab.


### -field IconID

Caller-supplied, can be one of the following:

<ul>
<li>
An icon resource identifier. This can be application-defined, or it can be one of the CPSUI-supplied, IDI_CPSUI-prefixed icon resource identifiers.

</li>
<li>
An icon handle. If a handle is specified, DPF_ICONID_AS_HICON must be set in the <b>Flags</b> member.

</li>
</ul>
The specified icon is displayed on the page tab. If this value is zero, an icon is not displayed.


### -field DUMMYUNIONNAME

 




#### - DlgTemplateID

Caller-supplied resource identifier for a dialog box template. This can refer to an application-supplied DIALOG resource, or it can be one of the following CPSUI-supplied identifiers (defined in compstui.h):

<table>
<tr>
<th>Identifier</th>
<th>Type of Page</th>
</tr>
<tr>
<td>
DP_STD_DOCPROPPAGE1

</td>
<td>
Nontreeview page, used for a print document's <b>Layout</b> page.

</td>
</tr>
<tr>
<td>
DP_STD_DOCPROPPAGE2

</td>
<td>
Nontreeview page, used for a print document's <b>Paper/Quality</b> page.

</td>
</tr>
<tr>
<td>
DP_STD_TREEVIEWPAGE

</td>
<td>
Generic treeview page.

</td>
</tr>
</table>
 

The CPSUI-supplied identifiers refer to templates that can display <a href="https://msdn.microsoft.com/library/windows/hardware/ff547142">CPSUI option types</a>. The page size for those templates is 252 by 216 dialog box units. For more information, see <a href="https://msdn.microsoft.com/de33cb29-3941-4232-bd61-d36fb04d69d3">CPSUI-Supplied Pages and Templates</a>.

This member is not used if DPF_USE_HDLGTEMPLATE is set in <b>Flags</b>.


#### - hDlgTemplate

Caller-supplied handle to a DLGTEMPLATE structure (described in the Microsoft Windows SDK documentation).

Used only if DPF_USE_HDLGTEMPLATE is set in <b>Flags</b>.


## -remarks



CPSUI creates a property sheet page by allocating a PROPSHEETPAGE structure and passing it to CreatePropertySheetPage (described in the Windows SDK documentation). If the caller has specified a DLGPROC-typed pointer to a dialog box procedure in <b>DlgProc</b>, that procedure is used for handling the page's window messages. If <b>DlgProc</b> is <b>NULL</b>, CPSUI's own dialog box procedures are used.

When the dialog box procedure pointed to by <b>DlgProc</b> is called with a message value of WM_INITDIALOG, it receives the PROPSHEETPAGE structure as input, and it also receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561844">PSPINFO</a> structure.

If a caller-supplied dialog box procedure handles a message, it should return a nonzero value. If the function does not handle the message it should return zero, which causes CPSUI to handle the message.

The PROPSHEETPAGE structure, the DLGPROC pointer type, and the WM_INITDIALOG message are described in the Windows SDK documentation.



