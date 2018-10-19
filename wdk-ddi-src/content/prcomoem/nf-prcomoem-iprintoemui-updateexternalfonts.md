---
UID: NF:prcomoem.IPrintOemUI.UpdateExternalFonts
title: IPrintOemUI::UpdateExternalFonts
author: windows-driver-content
description: The IPrintOemUI::UpdateExternalFonts method allows a user interface plug-in to update a printer's Unidrv Font Format Files (.uff file).
old-location: print\iprintoemui_updateexternalfonts.htm
tech.root: print
ms.assetid: 5c501305-fa5f-4466-9a9a-83f072d904b3
ms.date: 04/20/2018
ms.keywords: IPrintOemUI interface [Print Devices],UpdateExternalFonts method, IPrintOemUI.UpdateExternalFonts, IPrintOemUI::UpdateExternalFonts, UpdateExternalFonts, UpdateExternalFonts method [Print Devices], UpdateExternalFonts method [Print Devices],IPrintOemUI interface, prcomoem/IPrintOemUI::UpdateExternalFonts, print.iprintoemui_updateexternalfonts, print_unidrv-pscript_ui_e9f50923-c566-4e7f-997e-5788602d1083.xml
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	prcomoem.h
api_name:
-	IPrintOemUI.UpdateExternalFonts
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUI::UpdateExternalFonts


## -description


The <code>IPrintOemUI::UpdateExternalFonts</code> method allows a user interface plug-in to update a printer's <a href="https://msdn.microsoft.com/6e643703-ace1-4660-990c-3a9ca735829d">Unidrv Font Format Files</a> (.uff file).


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



A user interface plug-in must implement the <code>IPrintOemUI::UpdateExternalFonts</code> method if the plug-in is replacing Unidrv's default font installer. For more information, see <a href="https://msdn.microsoft.com/d753368d-b1c8-454e-a02b-131dc778e723">Customized Font Installers for Unidrv</a>.

The <code>IPrintOemUI::UpdateExternalFonts</code> method's purpose is to examine the list of installed cartridges (supplied by <i>pwstrCartridges</i>) and ensure that the .uff file specified by the "ExternalFontFile" registry value contains font descriptions for only the cartridge fonts contained in the installed cartridges. (This .uff file can also contain descriptions of <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">PCL</a>-downloadable soft fonts.)

Descriptions of cartridge fonts can be copied from the .uff file specified by the "ExtFontCartFile" registry value. For more information, see <a href="https://msdn.microsoft.com/6e643703-ace1-4660-990c-3a9ca735829d">Unidrv Font Format Files</a>.




## -see-also




<a href="https://msdn.microsoft.com/0ef635dd-9598-4356-94fc-7e5237df9bd9">IPrintOemUI</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554176">IPrintOemUI::FontInstallerDlgProc</a>
 

 

