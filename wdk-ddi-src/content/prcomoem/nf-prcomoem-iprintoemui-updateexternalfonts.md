---
UID: NF:prcomoem.IPrintOemUI.UpdateExternalFonts
title: IPrintOemUI::UpdateExternalFonts method
author: windows-driver-content
description: The IPrintOemUI::UpdateExternalFonts method allows a user interface plug-in to update a printer's Unidrv Font Format Files (.uff file).
old-location: print\iprintoemui_updateexternalfonts.htm
old-project: print
ms.assetid: 5c501305-fa5f-4466-9a9a-83f072d904b3
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: print.iprintoemui_updateexternalfonts, UpdateExternalFonts method [Print Devices], IPrintOemUI interface, IPrintOemUI::UpdateExternalFonts, UpdateExternalFonts method [Print Devices], IPrintOemUI interface [Print Devices], UpdateExternalFonts method, UpdateExternalFonts, print_unidrv-pscript_ui_e9f50923-c566-4e7f-997e-5788602d1083.xml, prcomoem/IPrintOemUI::UpdateExternalFonts, IPrintOemUI
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: prcomoem.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	prcomoem.h
apiname:
-	IPrintOemUI.UpdateExternalFonts
product: Windows
targetos: Windows
req.typenames: "*POEMPTOPTS, OEMPTOPTS"
req.product: Windows 10 or later.
---

# IPrintOemUI::UpdateExternalFonts method


## -description


The <code>IPrintOemUI::UpdateExternalFonts</code> method allows a user interface plug-in to update a printer's <a href="https://msdn.microsoft.com/6e643703-ace1-4660-990c-3a9ca735829d">Unidrv Font Format Files</a> (.uff file).


## -syntax


````
HRESULT UpdateExternalFonts(
   HANDLE hPrinter,
   HANDLE hHeap,
   PWSTR  pwstrCartridges
);
````


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554176">IPrintOemUI::FontInstallerDlgProc</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemUI::UpdateExternalFonts method%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

