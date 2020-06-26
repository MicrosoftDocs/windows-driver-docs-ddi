---
UID: NF:prcomoem.IPrintOemUni.TextOutAsBitmap
title: IPrintOemUni::TextOutAsBitmap (prcomoem.h)
description: The IPrintOemUni::TextOutAsBitmap method allows a rendering plug-in to create a bitmap image of a text string, in case a downloadable font is not available.
old-location: print\iprintoemuni_textoutasbitmap.htm
tech.root: print
ms.assetid: 2c144eb7-6279-490a-813c-6c0ae995c6ad
ms.date: 04/20/2018
keywords: ["IPrintOemUni::TextOutAsBitmap"]
ms.keywords: IPrintOemUni interface [Print Devices],TextOutAsBitmap method, IPrintOemUni.TextOutAsBitmap, IPrintOemUni::TextOutAsBitmap, TextOutAsBitmap, TextOutAsBitmap method [Print Devices], TextOutAsBitmap method [Print Devices],IPrintOemUni interface, prcomoem/IPrintOemUni::TextOutAsBitmap, print.iprintoemuni_textoutasbitmap, print_unidrv-pscript_rendering_41d6e02a-2a7b-4d78-95d6-fff6ae39b333.xml
f1_keywords:
 - "prcomoem/IPrintOemUni.TextOutAsBitmap"
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
- IPrintOemUni.TextOutAsBitmap
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUni::TextOutAsBitmap


## -description


The <code>IPrintOemUni::TextOutAsBitmap</code> method allows a rendering plug-in to create a bitmap image of a text string, in case a downloadable font is not available.


## -parameters




### -param pso

Pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/winddi/ns-winddi-_surfobj">SURFOBJ</a> structure that describes the surface on which to write. 


### -param pstro

Pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/winddi/ns-winddi-_strobj">STROBJ</a> structure that defines the glyphs to be rendered and the positions in which to place them. 


### -param pfo

Pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/winddi/ns-winddi-_fontobj">FONTOBJ</a> structure from which to retrieve information about the font and its glyphs. 


### -param pco

Pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/winddi/ns-winddi-_clipobj">CLIPOBJ</a> structure that defines the clip region through which all rendering must be done. The driver cannot affect any pixels outside the clip region. 


### -param prclExtra

Pointer to a RECTL structure. GDI always sets this parameter to <b>NULL</b> in calls to this function. It should be ignored by the driver. 


### -param prclOpaque

Pointer to a <a href="https://docs.microsoft.com/windows/win32/api/windef/ns-windef-rectl">RECTL</a> structure that represents a single opaque rectangle. This rectangle is bottom-right exclusive. Pixels within this rectangle (those that are not foreground and not clipped) are to be rendered with the opaque brush. This rectangle always bounds the text to be drawn. If this parameter is <b>NULL</b>, no opaque pixels are to be rendered. 


### -param pboFore

Pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/winddi/ns-winddi-_brushobj">BRUSHOBJ</a> structure that represents the brush object to be used for the foreground pixels. This brush will always be a solid color brush.


### -param pboOpaque

Pointer to a BRUSHOBJ structure that represents the opaque pixels. Both the foreground and background mix modes for this brush are assumed to be R2_COPYPEN. Unless the driver sets the GCAPS_ARBRUSHOPAQUE capabilities bit in the <i>flGraphicsCaps</i> member of the DEVINFO structure, it will always be called with a solid color brush. 


### -param pptlOrg

Pointer to a <a href="https://docs.microsoft.com/windows/win32/api/windef/ns-windef-pointl">POINTL</a> structure that defines the brush origin for both brushes.


### -param mix

The foreground and background raster operations (mix modes) for <i>pboFore</i>. 


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



The <code>IPrintOemUni::TextOutAsBitmap</code> method is called from Unidrv's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriveruni-drvunitextout">IPrintOemDriverUni::DrvUniTextOut</a> method, if that method cannot create the text string using downloadable fonts, either because the font is not available or is rotated. <code>IPrintOemUni::TextOutAsBitmap</code> should create a bitmap image of the text and send it to the print device.

The <code>IPrintOemUni::TextOutAsBitmap</code> method is optional. If a rendering plug-in implements this method, the plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-getimplementedmethod">IPrintOemUni::GetImplementedMethod</a> method must return S_OK when it receives "TextOutAsBitmap" as input.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriveruni-drvunitextout">IPrintOemDriverUni::DrvUniTextOut</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintoemuni">IPrintOemUni</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-getimplementedmethod">IPrintOemUni::GetImplementedMethod</a>
 

 

