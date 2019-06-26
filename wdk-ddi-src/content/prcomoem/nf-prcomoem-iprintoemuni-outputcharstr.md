---
UID: NF:prcomoem.IPrintOemUni.OutputCharStr
title: IPrintOemUni::OutputCharStr (prcomoem.h)
description: The IPrintOemUni::OutputCharStr method enables a rendering plug-in to control the printing of font glyphs.
old-location: print\iprintoemuni_outputcharstr.htm
tech.root: print
ms.assetid: 73518253-d65a-40ab-8735-44e92fbbed57
ms.date: 04/20/2018
ms.keywords: IPrintOemUni interface [Print Devices],OutputCharStr method, IPrintOemUni.OutputCharStr, IPrintOemUni::OutputCharStr, OutputCharStr, OutputCharStr method [Print Devices], OutputCharStr method [Print Devices],IPrintOemUni interface, prcomoem/IPrintOemUni::OutputCharStr, print.iprintoemuni_outputcharstr, print_unidrv-pscript_rendering_89b41d7b-5ceb-44a1-9b48-71751df6e40a.xml
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- prcomoem.h
api_name:
- IPrintOemUni.OutputCharStr
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUni::OutputCharStr


## -description


The <code>IPrintOemUni::OutputCharStr</code> method enables a rendering plug-in to control the printing of font glyphs.


## -parameters




### -param pdevobj

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/ns-printoem-_devobj">DEVOBJ</a> structure.


### -param pUFObj

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/ns-printoem-_unifontobj">UNIFONTOBJ</a> structure.


### -param dwType

Caller-supplied value indicating the type of glyph specifier array pointed to by <i>pGlyph</i>. Valid values are as follows:

<table>
<tr>
<th>Value</th>
<th>Definition</th>
</tr>
<tr>
<td>
TYPE_GLYPHHANDLE

</td>
<td>
The <i>pGlyph</i> array elements are glyph handles of type HGLYPH.

</td>
</tr>
<tr>
<td>
TYPE_GLYPHID

</td>
<td>
The <i>pGlyph</i> array elements are glyph identifiers of type DWORD.

</td>
</tr>
</table>
 


### -param dwCount

Caller-supplied value representing the number of glyph specifiers in the array pointed to by <i>pGlyph</i>.


### -param pGlyph

Caller-supplied pointer to an array of glyph specifiers, where the array element type is indicated by <i>dwType</i>.


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



The <code>IPrintOemUni::OutputCharStr</code> method is used for supporting printers that do not recognize the <a href="https://docs.microsoft.com/windows-hardware/drivers/">PCL</a>, CAPSL, or PPDS-formatted character output commands supported by Unidrv. Its purpose is to allow a rendering plug-in to control the printing of a font's glyphs, and to provide glyph substitutions if necessary.

If a rendering plug-in implements the <code>IPrintOemUni::OutputCharStr</code> method, Unidrv calls the method each time a string of characters is ready to be spooled.

The method receives an array of glyph specifiers. The value received for <i>dwType</i> indicates the identifier type.

If the specified font is a device font, the array contains glyph handles. The handles need to be translated to character codes or commands, and then sent to the print spooler to cause device glyphs to be printed.

If the specified font is a soft (TrueType) font, the array contains glyph identifiers. The identifiers represent previously downloaded glyphs that need to be printed.

If the specified font is a device font, the method must do the following:

<ol>
<li>
Allocate a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/ns-printoem-_getinfo_glyphstring">GETINFO_GLYPHSTRING</a> structure with <i>dwTypeIn</i> set to TYPE_GLYPHHANDLE and <i>dwTypeOut</i> set to TYPE_TRANSDATA.

</li>
<li>
Call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> function, passing the GETINFO_GLYPHSTRING structure as input, to obtain glyph translations as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prntfont/ns-prntfont-_transdata">TRANSDATA</a> structure contents.

</li>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemdriveruni-drvwritespoolbuf">IPrintOemDriverUni::DrvWriteSpoolBuf</a> to send TRANSDATA structure contents to the print spooler, in order to print the glyphs.

</li>
</ol>
If the specified font is a soft font, the method can just call <b>IPrintOemDriverUni::DrvWriteSpoolBuf</b> to send commands to the print spooler that will cause the specified previously-downloaded glyphs to be printed.

The <code>IPrintOemUni::OutputCharStr</code> method is optional. If a rendering plug-in implements this method, the plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemuni-getimplementedmethod">IPrintOemUni::GetImplementedMethod</a> method must return S_OK when it receives "OutputCharStr" as input.

For additional information see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/customized-font-management">Customized Font Management</a>.



