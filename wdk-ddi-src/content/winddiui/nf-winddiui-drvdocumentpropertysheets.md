---
UID: NF:winddiui.DrvDocumentPropertySheets
title: DrvDocumentPropertySheets function (winddiui.h)
description: A printer interface DLL's DrvDocumentPropertySheets function is responsible for creating property sheet pages that describe a print document's properties.
old-location: print\drvdocumentpropertysheets.htm
tech.root: print
ms.assetid: fc7e98ba-5c49-4c2d-af2e-b6c13757f6e6
ms.date: 04/20/2018
keywords: ["DrvDocumentPropertySheets function"]
ms.keywords: DrvDocumentPropertySheets, DrvDocumentPropertySheets function [Print Devices], print.drvdocumentpropertysheets, print_interface-graphics_00cc0beb-e6f1-41dd-ae0b-fd59a6d14465.xml, winddiui/DrvDocumentPropertySheets
f1_keywords:
 - "winddiui/DrvDocumentPropertySheets"
 - "DrvDocumentPropertySheets"
req.header: winddiui.h
req.include-header: Winddiui.h
req.target-type: Desktop
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
- winddiui.h
api_name:
- DrvDocumentPropertySheets
product:
- Windows
targetos: Windows
req.typenames: 
---

# DrvDocumentPropertySheets function


## -description


A printer interface DLL's <b>DrvDocumentPropertySheets</b> function is responsible for creating property sheet pages that describe a print document's properties.


## -parameters




### -param pPSUIInfo [in, optional]

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_propsheetui_info">PROPSHEETUI_INFO</a> structure. Can be <b>NULL</b> (see the following Remarks section).


### -param lParam

Caller-supplied integer value that is dependent on the contents of the <b>Reason</b> member of the PROPSHEETUI_INFO structure, as listed in the following table.

<table>
<tr>
<th>Reason value</th>
<th>Definition of <i>lParam</i></th>
</tr>
<tr>
<td>
PROPSHEETUI_REASON_INIT

</td>
<td>
Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_documentpropertyheader">DOCUMENTPROPERTYHEADER</a> structure.

</td>
</tr>
<tr>
<td>
All other reason values

</td>
<td>
See the description of the <i>lParam</i> parameter for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui">PFNPROPSHEETUI</a> function type.

(The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_documentpropertyheader">DOCUMENTPROPERTYHEADER</a> structure's address is contained in the <b>lParamInit</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_propsheetui_info">PROPSHEETUI_INFO</a> structure.)

</td>
</tr>
</table>
 


## -returns



If <i>pPSUIInfo</i> is <b>NULL</b>, and if either <i>lParam</i> -> <b>fMode</b> is zero or <i>lParam -</i>> <b>pdmOut</b> is <b>NULL</b>, this function should return the size, in bytes, of the printer's <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devmodew">DEVMODEW</a> structure. Otherwise, the function's return value is the same as that described in the ReturnValue section of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui">PFNPROPSHEETUI</a> function type. For more information, see the Remarks section. 




## -remarks



All <a href="https://docs.microsoft.com/windows-hardware/drivers/print/printer-interface-dll">printer interface DLLs</a> must provide a <b>DrvDocumentPropertySheets</b> function, which is defined using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui">PFNPROPSHEETUI</a> function type. The function's purpose is to call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet">ComPropSheet</a> function, provided by <a href="https://docs.microsoft.com/windows-hardware/drivers/print/common-property-sheet-user-interface">CPSUI</a>, to specify property sheet pages containing user-modifiable properties for print documents.

If the value received for the <i>pPSUIInfo</i> parameter is not <b>NULL</b>, the NT-based operating system print spooler is calling the function indirectly, through CPSUI. The following rules apply:

<ul>
<li>
The function should perform operations as described for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui">PFNPROPSHEETUI</a> function type.

</li>
<li>
Flags in the <b>fMode</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_documentpropertyheader">DOCUMENTPROPERTYHEADER</a> structure indicate which property sheet pages to display and whether the user should be allowed to modify a document's properties. The only flags that might be set are DM_IN_PROMPT (or DM_PROMPT), DM_ADVANCED, DM_NOPERMISSION, and DM_OUT_BUFFER (or DM_COPY).

</li>
</ul>
If the value received for the <i>pPSUIInfo</i> parameter is <b>NULL</b>, the print spooler is calling the function directly, without going through CPSUI. In this case, the <i>lParam</i> parameter contains the address of a DOCUMENTPROPERTYHEADER structure, and the following rules apply:

<ul>
<li>
If the <b>fMode</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_documentpropertyheader">DOCUMENTPROPERTYHEADER</a> structure is zero, or if the <b>pdmOut</b> member of the same structure is <b>NULL</b>, the function should return just the total size of the printer's <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devmodew">DEVMODEW</a> structure, including public and private structure members, in the DOCUMENTPROPERTYHEADER structure's <b>cbOut</b> member.

</li>
<li>
If the <b>fMode</b> member of the DOCUMENTPROPERTYHEADER structure is not zero, the function should perform the operations indicated by the <b>fMode</b> flags. The only flags that might be set are DM_IN_BUFFER (or DM_MODIFY), and DM_OUT_BUFFER (or DM_COPY).

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_documentpropertyheader">DOCUMENTPROPERTYHEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdevicepropertysheets">DrvDevicePropertySheets</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-documentpropertysheets">IPrintOemUI::DocumentPropertySheets</a>
 

 

