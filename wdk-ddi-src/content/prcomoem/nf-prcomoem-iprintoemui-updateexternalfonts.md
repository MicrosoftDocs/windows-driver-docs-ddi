---
UID: NF:prcomoem.IPrintOemUI.UpdateExternalFonts
title: IPrintOemUI::UpdateExternalFonts (prcomoem.h)
description: The IPrintOemUI::UpdateExternalFonts method allows a user interface plug-in to update a printer's Unidrv Font Format Files (.uff file).
old-location: print\iprintoemui_updateexternalfonts.htm
tech.root: print
ms.assetid: 5c501305-fa5f-4466-9a9a-83f072d904b3
ms.date: 04/20/2018
keywords: ["IPrintOemUI::UpdateExternalFonts"]
ms.keywords: IPrintOemUI interface [Print Devices],UpdateExternalFonts method, IPrintOemUI.UpdateExternalFonts, IPrintOemUI::UpdateExternalFonts, UpdateExternalFonts, UpdateExternalFonts method [Print Devices], UpdateExternalFonts method [Print Devices],IPrintOemUI interface, prcomoem/IPrintOemUI::UpdateExternalFonts, print.iprintoemui_updateexternalfonts, print_unidrv-pscript_ui_e9f50923-c566-4e7f-997e-5788602d1083.xml
f1_keywords:
 - "prcomoem/IPrintOemUI.UpdateExternalFonts"
 - "IPrintOemUI.UpdateExternalFonts"
req.header: prcomoem.h
req.include-header: Prcomoem.h
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
- COM
api_location:
- prcomoem.h
api_name:
- IPrintOemUI.UpdateExternalFonts
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUI::UpdateExternalFonts


## -description


The <code>IPrintOemUI::UpdateExternalFonts</code> method allows a user interface plug-in to update a printer's <a href="https://docs.microsoft.com/windows-hardware/drivers/print/customized-font-management">Unidrv Font Format Files</a> (.uff file).


## -parameters




### -param hPrinter

Caller-supplied printer handle.


### -param hHeap

Caller-supplied handle to heap memory the method can use for local storage.


### -param pwstrCartridges

Caller-supplied pointer to an array of strings representing the names of all cartridges currently installed on the printer.


## -returns



The method must return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The operation failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The method is not implemented.

</td>
</tr>
</table>
 




## -remarks



A user interface plug-in must implement the <code>IPrintOemUI::UpdateExternalFonts</code> method if the plug-in is replacing Unidrv's default font installer. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/customized-font-installers-for-unidrv">Customized Font Installers for Unidrv</a>.

The <code>IPrintOemUI::UpdateExternalFonts</code> method's purpose is to examine the list of installed cartridges (supplied by <i>pwstrCartridges</i>) and ensure that the .uff file specified by the "ExternalFontFile" registry value contains font descriptions for only the cartridge fonts contained in the installed cartridges. (This .uff file can also contain descriptions of <a href="https://docs.microsoft.com/windows-hardware/drivers/">PCL</a>-downloadable soft fonts.)

Descriptions of cartridge fonts can be copied from the .uff file specified by the "ExtFontCartFile" registry value. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/customized-font-management">Unidrv Font Format Files</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintoemui">IPrintOemUI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-fontinstallerdlgproc">IPrintOemUI::FontInstallerDlgProc</a>
 

 

