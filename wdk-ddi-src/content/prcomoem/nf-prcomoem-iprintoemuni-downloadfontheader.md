---
UID: NF:prcomoem.IPrintOemUni.DownloadFontHeader
title: IPrintOemUni::DownloadFontHeader (prcomoem.h)
description: The IPrintOemUni::DownloadFontHeader method allows a rendering plug-in for Unidrv to send a font's header information to a printer.
old-location: print\iprintoemuni_downloadfontheader.htm
tech.root: print
ms.assetid: 3d660d04-2872-44e6-ab76-719f5262bdd8
ms.date: 04/20/2018
keywords: ["IPrintOemUni::DownloadFontHeader"]
ms.keywords: DownloadFontHeader, DownloadFontHeader method [Print Devices], DownloadFontHeader method [Print Devices],IPrintOemUni interface, IPrintOemUni interface [Print Devices],DownloadFontHeader method, IPrintOemUni.DownloadFontHeader, IPrintOemUni::DownloadFontHeader, prcomoem/IPrintOemUni::DownloadFontHeader, print.iprintoemuni_downloadfontheader, print_unidrv-pscript_rendering_7ed24461-70a3-4446-9b3e-1fda13b0a29a.xml
f1_keywords:
 - "prcomoem/IPrintOemUni.DownloadFontHeader"
 - "IPrintOemUni.DownloadFontHeader"
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
- IPrintOemUni.DownloadFontHeader
targetos: Windows
req.typenames: 
---

# IPrintOemUni::DownloadFontHeader


## -description


The <code>IPrintOemUni::DownloadFontHeader</code> method allows a rendering plug-in for <a href="https://docs.microsoft.com/windows-hardware/drivers/">Unidrv</a> to send a font's header information to a printer.


## -parameters




### -param pdevobj

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_devobj">DEVOBJ</a> structure.


### -param pUFObj

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_unifontobj">UNIFONTOBJ</a> structure.


### -param pdwResult [out]

Receives a method-supplied value representing the amount of printer memory, in bytes, required to store the font header information. If the operation fails, the returned value should be zero.


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



The <code>IPrintOemUni::DownloadFontHeader</code> method is used for supporting soft fonts on printers that do not accept <a href="https://docs.microsoft.com/windows-hardware/drivers/">PCL</a> commands. Its purpose is to allow a rendering plug-in to obtain font header information from Unidrv and to send the information to the printer.

Information that might be required for constructing a non-<a href="https://docs.microsoft.com/windows-hardware/drivers/">PCL</a> font header can be obtained by:

<ul>
<li>
Referencing the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_unifontobj">UNIFONTOBJ</a> structure that is received as an input argument.

</li>
<li>
Calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> callback function to get the font's <a href="https://docs.microsoft.com/windows/desktop/api/winddi/ns-winddi-_fontobj">FONTOBJ</a> structure.

</li>
</ul>
The method should send the header information to the spooler by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriveruni-drvwritespoolbuf">IPrintOemDriverUni::DrvWriteSpoolBuf</a>.

The <code>IPrintOemUni::DownloadFontHeader</code> method is optional. If a rendering plug-in implements this method, the plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-getimplementedmethod">IPrintOemUni::GetImplementedMethod</a> method must return S_OK when it receives "DownloadFontHeader" as input.

If you implement the <code>IPrintOemUni::DownloadFontHeader</code> method, you must also implement the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-downloadcharglyph">IPrintOemUni::DownloadCharGlyph</a> method.

For additional information see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/customized-font-management">Customized Font Management</a>.



