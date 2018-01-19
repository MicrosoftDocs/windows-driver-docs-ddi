---
UID: NF:prcomoem.IPrintOemUni.OutputCharStr
title: IPrintOemUni::OutputCharStr method
author: windows-driver-content
description: The IPrintOemUni::OutputCharStr method enables a rendering plug-in to control the printing of font glyphs.
old-location: print\iprintoemuni_outputcharstr.htm
old-project: print
ms.assetid: 73518253-d65a-40ab-8735-44e92fbbed57
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintOemUni, IPrintOemUni::OutputCharStr, OutputCharStr
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
req.alt-api: IPrintOemUni.OutputCharStr
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

# IPrintOemUni::OutputCharStr method



## -description
The <code>IPrintOemUni::OutputCharStr</code> method enables a rendering plug-in to control the printing of font glyphs.



## -syntax

````
HRESULT OutputCharStr(
   PDEVOBJ     pdevobj,
   PUNIFONTOBJ pUFObj,
   DWORD       dwType,
   DWORD       dwCount,
   PVOID       pGlyph
);
````


## -parameters

### -param pdevobj 

Caller-supplied pointer to a <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure.


### -param pUFObj 

Caller-supplied pointer to a <a href="..\printoem\ns-printoem-_unifontobj.md">UNIFONTOBJ</a> structure.


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
The <code>IPrintOemUni::OutputCharStr</code> method is used for supporting printers that do not recognize the <a href="wdkgloss.p#wdkgloss.pcl#wdkgloss.pcl"><i>PCL</i></a>, CAPSL, or PPDS-formatted character output commands supported by Unidrv. Its purpose is to allow a rendering plug-in to control the printing of a font's glyphs, and to provide glyph substitutions if necessary.

If a rendering plug-in implements the <code>IPrintOemUni::OutputCharStr</code> method, Unidrv calls the method each time a string of characters is ready to be spooled.

The method receives an array of glyph specifiers. The value received for <i>dwType</i> indicates the identifier type.

If the specified font is a device font, the array contains glyph handles. The handles need to be translated to character codes or commands, and then sent to the print spooler to cause device glyphs to be printed.

If the specified font is a soft (TrueType) font, the array contains glyph identifiers. The identifiers represent previously downloaded glyphs that need to be printed.

If the specified font is a device font, the method must do the following:

Allocate a <a href="..\printoem\ns-printoem-_getinfo_glyphstring.md">GETINFO_GLYPHSTRING</a> structure with <i>dwTypeIn</i> set to TYPE_GLYPHHANDLE and <i>dwTypeOut</i> set to TYPE_TRANSDATA.

Call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> function, passing the GETINFO_GLYPHSTRING structure as input, to obtain glyph translations as <a href="..\prntfont\ns-prntfont-_transdata.md">TRANSDATA</a> structure contents.

Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff553138">IPrintOemDriverUni::DrvWriteSpoolBuf</a> to send TRANSDATA structure contents to the print spooler, in order to print the glyphs.

If the specified font is a soft font, the method can just call <b>IPrintOemDriverUni::DrvWriteSpoolBuf</b> to send commands to the print spooler that will cause the specified previously-downloaded glyphs to be printed.

The <code>IPrintOemUni::OutputCharStr</code> method is optional. If a rendering plug-in implements this method, the plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554253">IPrintOemUni::GetImplementedMethod</a> method must return S_OK when it receives "OutputCharStr" as input.

For additional information see <a href="https://msdn.microsoft.com/6e643703-ace1-4660-990c-3a9ca735829d">Customized Font Management</a>.</p>