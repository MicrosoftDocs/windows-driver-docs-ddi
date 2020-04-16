---
UID: NF:prcomoem.IPrintOemUni.DownloadCharGlyph
title: IPrintOemUni::DownloadCharGlyph (prcomoem.h)
description: The IPrintOemUni::DownloadCharGlyph method enables a rendering plug-in for Unidrv to send a character glyph for a specified soft font to the printer.
old-location: print\iprintoemuni_downloadcharglyph.htm
tech.root: print
ms.assetid: 1ce7ebaa-759e-418a-af07-e530b1102567
ms.date: 04/20/2018
keywords: ["IPrintOemUni::DownloadCharGlyph"]
ms.keywords: DownloadCharGlyph, DownloadCharGlyph method [Print Devices], DownloadCharGlyph method [Print Devices],IPrintOemUni interface, IPrintOemUni interface [Print Devices],DownloadCharGlyph method, IPrintOemUni.DownloadCharGlyph, IPrintOemUni::DownloadCharGlyph, prcomoem/IPrintOemUni::DownloadCharGlyph, print.iprintoemuni_downloadcharglyph, print_unidrv-pscript_rendering_da86807b-5b3c-41af-8504-337da544dd93.xml
f1_keywords:
 - "prcomoem/IPrintOemUni.DownloadCharGlyph"
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
- IPrintOemUni.DownloadCharGlyph
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUni::DownloadCharGlyph


## -description


The <code>IPrintOemUni::DownloadCharGlyph</code> method enables a rendering plug-in for Unidrv to send a character glyph for a specified soft font to the printer.


## -parameters




### -param pdevobj

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_devobj">DEVOBJ</a> structure.


### -param pUFObj

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_unifontobj">UNIFONTOBJ</a> structure.


### -param hGlyph

Caller-supplied glyph handle.


### -param pdwWidth

Caller-supplied pointer to receive the method-supplied width of the character.


### -param pdwResult [out]

Receives a method-supplied value representing the amount of printer memory, in bytes, required to store the character glyph. If the operation fails, the returned value should be zero.


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
The operation failed

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



The <code>IPrintOemUni::DownloadCharGlyph</code> method is used for supporting soft fonts on printers that do not accept <a href="https://docs.microsoft.com/windows-hardware/drivers/">PCL</a> commands. Its purpose is to enable a rendering plug-in to send a character glyph to the printer.

If a rendering plug-in implements the  <code>IPrintOemUni::DownloadCharGlyph</code> method, Unidrv calls the method immediately after sending the command string specified by the CmdSetCharCode command entry, which is contained in the printer's <a href="https://docs.microsoft.com/windows-hardware/drivers/">GPD</a> file. (GPD files are described in <a href="https://docs.microsoft.com/windows-hardware/drivers/print/microsoft-universal-printer-driver">Microsoft Universal Printer Driver</a>.) The method should do the following:

<ul>
<li>
Call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> function to obtain the glyph image specified by <i>hGlyph</i>.

</li>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriveruni-drvwritespoolbuf">IPrintOemDriverUni::DrvWriteSpoolBuf</a> to send the glyph to the printer.

</li>
<li>
Call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> function again to obtain the glyph's width, then store the width in the address pointed to by <i>pdwWidth</i>. 

</li>
<li>
Return the amount of printer memory required to store the glyph by placing it in the location specified by <i>pdwResult</i>.

</li>
</ul>
The <code>IPrintOemUni::DownloadCharGlyph</code> method is optional. If a rendering plug-in implements this method, the plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-getimplementedmethod">IPrintOemUni::GetImplementedMethod</a> method must return S_OK when it receives "DownloadCharGlyph" as input.

If you implement the <code>IPrintOemUni::DownloadCharGlyph</code> method, you must also implement the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-downloadfontheader">IPrintOemUni::DownloadFontHeader</a> method.

For additional information see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/customized-font-management">Customized Font Management</a>.



