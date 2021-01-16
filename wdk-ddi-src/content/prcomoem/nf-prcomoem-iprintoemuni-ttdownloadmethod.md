---
UID: NF:prcomoem.IPrintOemUni.TTDownloadMethod
title: IPrintOemUni::TTDownloadMethod (prcomoem.h)
description: The IPrintOemUni::TTDownloadMethod method enables a rendering plug-in to indicate the format that Unidrv should use for a specified TrueType soft font.
old-location: print\iprintoemuni_ttdownloadmethod.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IPrintOemUni::TTDownloadMethod"]
ms.keywords: IPrintOemUni interface [Print Devices],TTDownloadMethod method, IPrintOemUni.TTDownloadMethod, IPrintOemUni::TTDownloadMethod, TTDownloadMethod, TTDownloadMethod method [Print Devices], TTDownloadMethod method [Print Devices],IPrintOemUni interface, prcomoem/IPrintOemUni::TTDownloadMethod, print.iprintoemuni_ttdownloadmethod, print_unidrv-pscript_rendering_8a4dc2b9-3318-492d-8585-9fb5e6d8fd9d.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrintOemUni::TTDownloadMethod
 - prcomoem/IPrintOemUni::TTDownloadMethod
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - prcomoem.h
api_name:
 - IPrintOemUni::TTDownloadMethod
---

# IPrintOemUni::TTDownloadMethod


## -description

The <code>IPrintOemUni::TTDownloadMethod</code> method enables a rendering plug-in to indicate the format that Unidrv should use for a specified TrueType soft font.

## -parameters

### -param pdevobj

Caller-supplied pointer to a <a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_devobj">DEVOBJ</a> structure.

### -param pUFObj

Caller-supplied pointer to a <a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_unifontobj">UNIFONTOBJ</a> structure.

### -param pdwResult 

[out]
Receives one of the following method-supplied constant values:

<table>
<tr>
<th>Value</th>
<th>Definition</th>
</tr>
<tr>
<td>
TTDOWNLOAD_BITMAP

</td>
<td>
Unidrv should download the specified font as bitmaps.

</td>
</tr>
<tr>
<td>
TTDOWNLOAD_DONTCARE

</td>
<td>
Unidrv can select the font format.

</td>
</tr>
<tr>
<td>
TTDOWNLOAD_GRAPHICS

</td>
<td>
Unidrv should print TrueType fonts as graphics, instead of downloading the font.

</td>
</tr>
<tr>
<td>
TTDOWNLOAD_TTOUTLINE

</td>
<td>
Unidrv should download the specified font as outlines. For more information, see the following Remarks section.

</td>
</tr>
</table>

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

The <code>IPrintOemUni::TTDownloadMethod</code> method's purpose is to allow a rendering plug-in to specify a printer's preferred format for a specified TrueType soft font.

If a rendering plug-in implements the <code>IPrintOemUni::TTDownloadMethod</code> method, Unidrv calls the method each time it is ready to send a TrueType font to the print spooler. Unidrv specifies the font type and the <code>IPrintOemUni::TTDownloadMethod</code> method should specify the printer's preferred format in the location pointed to by <i>pdwResult</i>.

The method should not return TTDOWNLOAD_TTOUTLINE unless the printer can rasterize TrueType fonts. The rendering plug-in is responsible for reading and parsing TrueType font files. Pointers to TrueType font files can be obtained by calling <a href="/windows/win32/api/winddi/nf-winddi-fontobj_pvtruetypefontfile">FONTOBJ_pvTrueTypeFontFile</a>.

The <code>IPrintOemUni::TTDownloadMethod</code> method is optional. If a rendering plug-in implements this method, the plug-in's <a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-getimplementedmethod">IPrintOemUni::GetImplementedMethod</a> method must return S_OK when it receives "TTDownLoadMethod" as input.

For additional information see <a href="/windows-hardware/drivers/print/customized-font-management">Customized Font Management</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_devobj">DEVOBJ</a>



<a href="/windows/win32/api/winddi/nf-winddi-fontobj_pvtruetypefontfile">FONTOBJ_pvTrueTypeFontFile</a>



<a href="/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintoemuni">IPrintOemUni</a>



<a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-getimplementedmethod">IPrintOemUni::GetImplementedMethod</a>



<a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_unifontobj">UNIFONTOBJ</a>

