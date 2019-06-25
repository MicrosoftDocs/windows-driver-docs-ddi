---
UID: NS:compstui._COMPROPSHEETUI
title: _COMPROPSHEETUI (compstui.h)
description: The COMPROPSHEETUI structure is used as an input parameter to CPSUI's ComPropSheet function, if the function code is CPSFUNC_ADD_PCOMPROPSHEETUI. All structure members must be supplied by the caller of ComPropSheet.
old-location: print\compropsheetui.htm
tech.root: print
ms.assetid: 7ebf46b7-5c31-482e-8644-a3d81f7dc5cc
ms.date: 04/20/2018
ms.keywords: "*PCOMPROPSHEETUI, COMPROPSHEETUI, COMPROPSHEETUI structure [Print Devices], PCOMPROPSHEETUI, PCOMPROPSHEETUI structure pointer [Print Devices], _COMPROPSHEETUI, compstui/COMPROPSHEETUI, compstui/PCOMPROPSHEETUI, cpsuifnc_9b1aab20-fcd7-41b5-8bc5-959ae606d6b8.xml, print.compropsheetui"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- compstui.h
api_name:
- COMPROPSHEETUI
product:
- Windows
targetos: Windows
req.typenames: COMPROPSHEETUI, *PCOMPROPSHEETUI
---

# _COMPROPSHEETUI structure


## -description


The COMPROPSHEETUI structure is used as an input parameter to CPSUI's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/compstui/nc-compstui-pfncompropsheet">ComPropSheet</a> function, if the function code is <a href="https://docs.microsoft.com/previous-versions/ff546388(v=vs.85)">CPSFUNC_ADD_PCOMPROPSHEETUI</a>. All structure members must be supplied by the caller of <i>ComPropSheet</i>.


## -struct-fields




### -field cbSize

Caller-supplied size, in bytes, of the COMPROPSHEETUI structure.


### -field Flags

Optional caller-supplied bit flags, as described in the following list:





#### CPSUIF_ABOUT_CALLBACK

If set, the page's callback function (pointed to by the structure's <b>pfnCallback</b> member), supports CPSUICB_REASON_ABOUT, so CPSUI will call the callback function if the user clicks on the page's <b>About</b> button. (CPSUI supplies an <b>About</b> button for each treeview root node.)





#### CPSUIF_ICONID_AS_HICON

If set, the structure's <b>IconID</b> member contains an icon handle.

If not set, the <b>IconID</b> member contains an icon resource identifier.





#### CPSUIF_UPDATE_PERMISSION

If set, the page's option values can be modified by the user.


### -field hInstCaller

Caller-supplied module instance handle, received by the DLL's entry point function.


### -field pCallerName

Caller-supplied pointer to a NULL-terminated text string representing the application's name. (For a printer interface DLL, this should be the driver's name, such as "PostScript Driver".)


### -field UserData

Optional caller-supplied value, which CPSUI places in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/compstui/ns-compstui-_cpsuicbparam">CPSUICBPARAM</a> structure's <b>UserData</b> member when calling the function pointed to by <b>pfnCallBack</b>.


### -field pHelpFile

Caller-supplied pointer to a NULL-terminated text string representing a path to a help file. For printer interface DLLs, this is typically the help file path obtained by calling GetPrinterDriver (described in the Microsoft Windows SDK documentation).

The help file is indexed by values contained in the <b>HelpIndex</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/compstui/ns-compstui-_optitem">OPTITEM</a> structures.


### -field pfnCallBack

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/compstui/nc-compstui-_cpsuicallback">_CPSUICALLBACK</a>-typed callback function, which CPSUI calls when a user modifies the page's option values.

Can be used only if <b>pDlgPage</b> identifies a CPSUI-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/compstui/ns-compstui-_dlgpage">DLGPAGE</a> structure, or if the <b>DlgProc</b> member of an application-supplied DLGPAGE structure is <b>NULL</b>.


### -field pOptItem

Caller-supplied pointer to an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/compstui/ns-compstui-_optitem">OPTITEM</a> structures describing the page's options.


### -field pDlgPage

This member specifies <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/compstui/ns-compstui-_dlgpage">DLGPAGE</a> structures that describe pages to be added to the property sheet. It can be either of the following:

<ul>
<li>
A pointer to an array of DLGPAGE structures.

</li>
<li>
One of the pointers that is described in the following list. These pointers reference predefined DLGPAGE structures, supplied by CPSUI for use by printer interface DLLs.

<dl>
<dt><a id="CPSUI_PDLGPAGE_ADVDOCPROP"></a><a id="cpsui_pdlgpage_advdocprop"></a>CPSUI_PDLGPAGE_ADVDOCPROP</dt>
<dd>
Defines one treeview page whose tab reads <b>Advanced</b>.

For use only by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/nf-winddiui-drvdocumentpropertysheets">DrvDocumentPropertySheets</a> function.

</dd>
</dl>


<dl>
<dt><a id="CPSUI_PDLGPAGE_DOCPROP"></a><a id="cpsui_pdlgpage_docprop"></a>CPSUI_PDLGPAGE_DOCPROP</dt>
<dd>
Defines three pages, whose tabs are <b>Layout</b>, <b>Paper/Quality</b>, and <b>Advanced</b>. The <b>Advanced</b> page is a treeview.

For use only by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/nf-winddiui-drvdocumentpropertysheets">DrvDocumentPropertySheets</a> function.

</dd>
</dl>


<dl>
<dt><a id="CPSUI_PDLGPAGE_PRINTERPROP"></a><a id="cpsui_pdlgpage_printerprop"></a>CPSUI_PDLGPAGE_PRINTERPROP</dt>
<dd>
Defines one treeview page whose tab reads <b>Device Settings</b>.

For use only by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/nf-winddiui-drvdevicepropertysheets">DrvDevicePropertySheets</a> function.

</dd>
</dl>


<dl>
<dt><a id="CPSUI_PDLGPAGE_TREEVIEWONLY"></a><a id="cpsui_pdlgpage_treeviewonly"></a>CPSUI_PDLGPAGE_TREEVIEWONLY</dt>
<dd>
Defines one treeview page.

</dd>
</dl>


</li>
</ul>

### -field cOptItem

Caller-supplied number of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/compstui/ns-compstui-_optitem">OPTITEM</a> structures pointed to by <b>pOptItem</b>.


### -field cDlgPage

Caller-supplied number of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/compstui/ns-compstui-_dlgpage">DLGPAGE</a> structures pointed to by <b>pDlgPage</b>. Not used if <b>pDlgPage</b> specifies a predefined CPSUI_PDLGPAGE-prefixed structure.


### -field IconID

Caller-supplied, can be one of the following:

<ul>
<li>
An icon resource identifier. This can be application-defined, or it can be one of the CPSUI-supplied, IDI_CPSUI-prefixed icon resource identifiers.

</li>
<li>
An icon handle. If a handle is specified, CPSUIF_ICONID_AS_HICON must be set in the <b>Flags</b> member.

</li>
</ul>
The specified icon is displayed in the root node of the property sheet page's treeview.


### -field pOptItemName

Caller-supplied pointer to a NULL-terminated string to be displayed in the root node of the property sheet page's treeview. For printer interface DLLs, this string typically represents a printer device type, such as "HP 4si".


### -field CallerVersion

Caller-supplied version number, representing the calling application's current version. The high byte identifies the major version, and the low byte is the minor version. For example, a <b>CallerVersion</b> value of 0x310 specifies a caller version number of 3.16. The version number is displayed when a user clicks on a page's <b>About</b> button.


### -field OptItemVersion

Caller-supplied version number, representing the root-level option item's current version. For printer interface DLLs, this typically represents a printer device version. The high byte identifies the major version, and the low byte is the minor version. For example, an <b>OptItemVersion</b> value of 0x3ff specifies a caller version number of 3.255. The version number is displayed when a user clicks on a page's <b>About</b> button.


### -field dwReserved

Reserved. This array must be set to zero.

