---
UID: NF:winddiui.DrvDocumentPropertySheets
title: DrvDocumentPropertySheets function
author: windows-driver-content
description: A printer interface DLL's DrvDocumentPropertySheets function is responsible for creating property sheet pages that describe a print document's properties.
old-location: print\drvdocumentpropertysheets.htm
old-project: print
ms.assetid: fc7e98ba-5c49-4c2d-af2e-b6c13757f6e6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DrvDocumentPropertySheets, DrvDocumentPropertySheets function [Print Devices], print.drvdocumentpropertysheets, print_interface-graphics_00cc0beb-e6f1-41dd-ae0b-fd59a6d14465.xml, winddiui/DrvDocumentPropertySheets
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	winddiui.h
api_name:
-	DrvDocumentPropertySheets
product: Windows
targetos: Windows
req.typenames: WINBIO_VERSION, *PWINBIO_VERSION
req.product: Windows 10 or later.
---

# DrvDocumentPropertySheets function


## -description


A printer interface DLL's <b>DrvDocumentPropertySheets</b> function is responsible for creating property sheet pages that describe a print document's properties.


## -syntax


````
LONG DrvDocumentPropertySheets(
  _In_opt_ PPROPSHEETUI_INFO pPSUIInfo,
           LPARAM            lParam
);
````


## -parameters




### -param pPSUIInfo [in, optional]

Caller-supplied pointer to a <a href="..\compstui\ns-compstui-_propsheetui_info.md">PROPSHEETUI_INFO</a> structure. Can be <b>NULL</b> (see the following Remarks section).


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
Pointer to a <a href="..\winddiui\ns-winddiui-_documentpropertyheader.md">DOCUMENTPROPERTYHEADER</a> structure.

</td>
</tr>
<tr>
<td>
All other reason values

</td>
<td>
See the description of the <i>lParam</i> parameter for the <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a> function type.

(The <a href="..\winddiui\ns-winddiui-_documentpropertyheader.md">DOCUMENTPROPERTYHEADER</a> structure's address is contained in the <b>lParamInit</b> member of the <a href="..\compstui\ns-compstui-_propsheetui_info.md">PROPSHEETUI_INFO</a> structure.)

</td>
</tr>
</table>
 


## -returns



If <i>pPSUIInfo</i> is <b>NULL</b>, and if either <i>lParam</i> -&gt; <b>fMode</b> is zero or <i>lParam -</i>&gt; <b>pdmOut</b> is <b>NULL</b>, this function should return the size, in bytes, of the printer's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure. Otherwise, the function's return value is the same as that described in the ReturnValue section of the <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a> function type. For more information, see the Remarks section. 




## -remarks



All <a href="https://msdn.microsoft.com/2a8cf38f-8e27-4e08-9c0f-5d1a4cd854ac">printer interface DLLs</a> must provide a <b>DrvDocumentPropertySheets</b> function, which is defined using the <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a> function type. The function's purpose is to call the <a href="..\compstui\nc-compstui-pfncompropsheet.md">ComPropSheet</a> function, provided by <a href="https://msdn.microsoft.com/7af3435a-19e0-40a1-9f94-319d9d323856">CPSUI</a>, to specify property sheet pages containing user-modifiable properties for print documents.

If the value received for the <i>pPSUIInfo</i> parameter is not <b>NULL</b>, the NT-based operating system print spooler is calling the function indirectly, through CPSUI. The following rules apply:

<ul>
<li>
The function should perform operations as described for the <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a> function type.

</li>
<li>
Flags in the <b>fMode</b> member of the <a href="..\winddiui\ns-winddiui-_documentpropertyheader.md">DOCUMENTPROPERTYHEADER</a> structure indicate which property sheet pages to display and whether the user should be allowed to modify a document's properties. The only flags that might be set are DM_IN_PROMPT (or DM_PROMPT), DM_ADVANCED, DM_NOPERMISSION, and DM_OUT_BUFFER (or DM_COPY).

</li>
</ul>
If the value received for the <i>pPSUIInfo</i> parameter is <b>NULL</b>, the print spooler is calling the function directly, without going through CPSUI. In this case, the <i>lParam</i> parameter contains the address of a DOCUMENTPROPERTYHEADER structure, and the following rules apply:

<ul>
<li>
If the <b>fMode</b> member of the <a href="..\winddiui\ns-winddiui-_documentpropertyheader.md">DOCUMENTPROPERTYHEADER</a> structure is zero, or if the <b>pdmOut</b> member of the same structure is <b>NULL</b>, the function should return just the total size of the printer's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure, including public and private structure members, in the DOCUMENTPROPERTYHEADER structure's <b>cbOut</b> member.

</li>
<li>
If the <b>fMode</b> member of the DOCUMENTPROPERTYHEADER structure is not zero, the function should perform the operations indicated by the <b>fMode</b> flags. The only flags that might be set are DM_IN_BUFFER (or DM_MODIFY), and DM_OUT_BUFFER (or DM_COPY).

</li>
</ul>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554173">IPrintOemUI::DocumentPropertySheets</a>



<a href="..\winddiui\nf-winddiui-drvdevicepropertysheets.md">DrvDevicePropertySheets</a>



<a href="..\winddiui\ns-winddiui-_documentpropertyheader.md">DOCUMENTPROPERTYHEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20DrvDocumentPropertySheets function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

