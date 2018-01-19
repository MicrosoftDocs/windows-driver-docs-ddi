---
UID: NF:prcomoem.IPrintOemUI.FontInstallerDlgProc
title: IPrintOemUI::FontInstallerDlgProc method
author: windows-driver-content
description: A user interface plug-in's IPrintOemUI::FontInstallerDlgProc method replaces the Unidrv font installer's user interface.
old-location: print\iprintoemui_fontinstallerdlgproc.htm
old-project: print
ms.assetid: 6f63d48d-7c2f-4531-b6db-fd4fdcfbce27
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintOemUI, IPrintOemUI::FontInstallerDlgProc, FontInstallerDlgProc
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
req.alt-api: IPrintOemUI.FontInstallerDlgProc
req.alt-loc: prcomoem.h
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
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemUI::FontInstallerDlgProc method



## -description
A user interface plug-in's <code>IPrintOemUI::FontInstallerDlgProc</code> method replaces the Unidrv font installer's user interface.



## -syntax

````
HRESULT FontInstallerDlgProc(
   HWND   hWnd,
   UINT   usMsg,
   WPARAM wParam,
   LPARAM lParam
);
````


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
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation succeeded.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The operation failed.
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The method is not implemented.

 


## -remarks
A user interface plug-in can implement the <code>IPrintOemUI::FontInstallerDlgProc</code> method as a means of replacing Unidrv's font installer. For more information, see <a href="https://msdn.microsoft.com/d753368d-b1c8-454e-a02b-131dc778e723">Customized Font Installers for Unidrv</a>.

The <code>IPrintOemUI::FontInstallerDlgProc</code> method is used by Unidrv as a dialog box procedure, and its address is passed to <b>DialogBoxParam</b> (described in the Microsoft Windows SDK documentation) when a user invokes the font installer from Unidrv's user interface.

If the message received for <i>usMsg</i> is WM_INIT or WM_USER+WM_FI_NAME, <i>lParam</i> points to an <a href="..\prntfont\ns-prntfont-_oemfontinstparam.md">OEMFONTINSTPARAM</a> structure.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554188">IPrintOemUI::UpdateExternalFonts</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemUI::FontInstallerDlgProc method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

