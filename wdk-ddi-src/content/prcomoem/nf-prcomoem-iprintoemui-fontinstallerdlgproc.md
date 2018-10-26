---
UID: NF:prcomoem.IPrintOemUI.FontInstallerDlgProc
title: IPrintOemUI::FontInstallerDlgProc
author: windows-driver-content
description: A user interface plug-in's IPrintOemUI::FontInstallerDlgProc method replaces the Unidrv font installer's user interface.
old-location: print\iprintoemui_fontinstallerdlgproc.htm
tech.root: print
ms.assetid: 6f63d48d-7c2f-4531-b6db-fd4fdcfbce27
ms.date: 04/20/2018
ms.keywords: FontInstallerDlgProc, FontInstallerDlgProc method [Print Devices], FontInstallerDlgProc method [Print Devices],IPrintOemUI interface, IPrintOemUI interface [Print Devices],FontInstallerDlgProc method, IPrintOemUI.FontInstallerDlgProc, IPrintOemUI::FontInstallerDlgProc, prcomoem/IPrintOemUI::FontInstallerDlgProc, print.iprintoemui_fontinstallerdlgproc, print_unidrv-pscript_ui_f5a028b9-eb7b-4d07-81e8-d7aadc5b8ceb.xml
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
-	IPrintOemUI.FontInstallerDlgProc
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUI::FontInstallerDlgProc


## -description


A user interface plug-in's <code>IPrintOemUI::FontInstallerDlgProc</code> method replaces the Unidrv font installer's user interface.


## -parameters




### -param hWnd

Window handle.


### -param usMsg

Message identifier.


### -param wParam

First message parameter.


### -param lParam

Second message parameter.


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



A user interface plug-in can implement the <code>IPrintOemUI::FontInstallerDlgProc</code> method as a means of replacing Unidrv's font installer. For more information, see <a href="https://msdn.microsoft.com/d753368d-b1c8-454e-a02b-131dc778e723">Customized Font Installers for Unidrv</a>.

The <code>IPrintOemUI::FontInstallerDlgProc</code> method is used by Unidrv as a dialog box procedure, and its address is passed to <b>DialogBoxParam</b> (described in the Microsoft Windows SDK documentation) when a user invokes the font installer from Unidrv's user interface.

If the message received for <i>usMsg</i> is WM_INIT or WM_USER+WM_FI_NAME, <i>lParam</i> points to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff557731">OEMFONTINSTPARAM</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/0ef635dd-9598-4356-94fc-7e5237df9bd9">IPrintOemUI</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554188">IPrintOemUI::UpdateExternalFonts</a>
 

 

