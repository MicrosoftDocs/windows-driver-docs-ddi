---
UID: NF:prcomoem.IPrintOemUni.DownloadCharGlyph
title: IPrintOemUni::DownloadCharGlyph method
author: windows-driver-content
description: The IPrintOemUni::DownloadCharGlyph method enables a rendering plug-in for Unidrv to send a character glyph for a specified soft font to the printer.
old-location: print\iprintoemuni_downloadcharglyph.htm
old-project: print
ms.assetid: 1ce7ebaa-759e-418a-af07-e530b1102567
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintOemUni, IPrintOemUni::DownloadCharGlyph, DownloadCharGlyph
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
req.alt-api: IPrintOemUni.DownloadCharGlyph
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

# IPrintOemUni::DownloadCharGlyph method



## -description
The <code>IPrintOemUni::DownloadCharGlyph</code> method enables a rendering plug-in for Unidrv to send a character glyph for a specified soft font to the printer.



## -syntax

````
HRESULT DownloadCharGlyph(
        PDEVOBJ     pdevobj,
        PUNIFONTOBJ pUFObj,
        HGLYPH      hGlyph,
        PDWORD      pdwWidth,
  [out] DWORD       *pdwResult
);
````


## -parameters

### -param pdevobj 

Caller-supplied pointer to a <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure.


### -param pUFObj 

Caller-supplied pointer to a <a href="..\printoem\ns-printoem-_unifontobj.md">UNIFONTOBJ</a> structure.


### -param hGlyph 

Caller-supplied glyph handle.


### -param pdwWidth 

Caller-supplied pointer to receive the method-supplied width of the character.


### -param pdwResult [out]

Receives a method-supplied value representing the amount of printer memory, in bytes, required to store the character glyph. If the operation fails, the returned value should be zero.


## -returns
The method must return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation succeeded.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The operation failed
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The method is not implemented.

 


## -remarks
The <code>IPrintOemUni::DownloadCharGlyph</code> method is used for supporting soft fonts on printers that do not accept <a href="wdkgloss.p#wdkgloss.pcl#wdkgloss.pcl"><i>PCL</i></a> commands. Its purpose is to enable a rendering plug-in to send a character glyph to the printer.

If a rendering plug-in implements the  <code>IPrintOemUni::DownloadCharGlyph</code> method, Unidrv calls the method immediately after sending the command string specified by the CmdSetCharCode command entry, which is contained in the printer's <a href="wdkgloss.g#wdkgloss.generic_printer_description__gpd_#wdkgloss.generic_printer_description__gpd_"><i>GPD</i></a> file. (GPD files are described in <a href="https://msdn.microsoft.com/1f5d68a1-3552-44a9-a0c5-b3ec5fe22a22">Microsoft Universal Printer Driver</a>.) The method should do the following:

Call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> function to obtain the glyph image specified by <i>hGlyph</i>.

Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff553138">IPrintOemDriverUni::DrvWriteSpoolBuf</a> to send the glyph to the printer.

Call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> function again to obtain the glyph's width, then store the width in the address pointed to by <i>pdwWidth</i>. 

Return the amount of printer memory required to store the glyph by placing it in the location specified by <i>pdwResult</i>.

The <code>IPrintOemUni::DownloadCharGlyph</code> method is optional. If a rendering plug-in implements this method, the plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554253">IPrintOemUni::GetImplementedMethod</a> method must return S_OK when it receives "DownloadCharGlyph" as input.

If you implement the <code>IPrintOemUni::DownloadCharGlyph</code> method, you must also implement the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554242">IPrintOemUni::DownloadFontHeader</a> method.

For additional information see <a href="https://msdn.microsoft.com/6e643703-ace1-4660-990c-3a9ca735829d">Customized Font Management</a>.</p>