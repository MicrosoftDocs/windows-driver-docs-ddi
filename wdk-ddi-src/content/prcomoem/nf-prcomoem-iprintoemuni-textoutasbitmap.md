---
UID: NF:prcomoem.IPrintOemUni.TextOutAsBitmap
title: IPrintOemUni::TextOutAsBitmap method
author: windows-driver-content
description: The IPrintOemUni::TextOutAsBitmap method allows a rendering plug-in to create a bitmap image of a text string, in case a downloadable font is not available.
old-location: print\iprintoemuni_textoutasbitmap.htm
old-project: print
ms.assetid: 2c144eb7-6279-490a-813c-6c0ae995c6ad
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintOemUni, IPrintOemUni::TextOutAsBitmap, TextOutAsBitmap
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
req.alt-api: IPrintOemUni.TextOutAsBitmap
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

# IPrintOemUni::TextOutAsBitmap method



## -description
The <code>IPrintOemUni::TextOutAsBitmap</code> method allows a rendering plug-in to create a bitmap image of a text string, in case a downloadable font is not available.



## -syntax

````
HRESULT TextOutAsBitmap(
   SURFOBJ  *pso,
   STROBJ   *pstro,
   FONTOBJ  *pfo,
   CLIPOBJ  *pco,
   RECTL    *prclExtra,
   RECTL    *prclOpaque,
   BRUSHOBJ *pboFore,
   BRUSHOBJ *pboOpaque,
   POINTL   *pptlOrg,
   MIX      mix
);
````


## -parameters

### -param pso 

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569901">SURFOBJ</a> structure that describes the surface on which to write. 


### -param pstro 

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569738">STROBJ</a> structure that defines the glyphs to be rendered and the positions in which to place them. 


### -param pfo 

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565974">FONTOBJ</a> structure from which to retrieve information about the font and its glyphs. 


### -param pco 

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539417">CLIPOBJ</a> structure that defines the clip region through which all rendering must be done. The driver cannot affect any pixels outside the clip region. 


### -param prclExtra 

Pointer to a RECTL structure. GDI always sets this parameter to <b>NULL</b> in calls to this function. It should be ignored by the driver. 


### -param prclOpaque 

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569236">RECTL</a> structure that represents a single opaque rectangle. This rectangle is bottom-right exclusive. Pixels within this rectangle (those that are not foreground and not clipped) are to be rendered with the opaque brush. This rectangle always bounds the text to be drawn. If this parameter is <b>NULL</b>, no opaque pixels are to be rendered. 


### -param pboFore 

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff538261">BRUSHOBJ</a> structure that represents the brush object to be used for the foreground pixels. This brush will always be a solid color brush.


### -param pboOpaque 

Pointer to a BRUSHOBJ structure that represents the opaque pixels. Both the foreground and background mix modes for this brush are assumed to be R2_COPYPEN. Unless the driver sets the GCAPS_ARBRUSHOPAQUE capabilities bit in the <i>flGraphicsCaps</i> member of the DEVINFO structure, it will always be called with a solid color brush. 


### -param pptlOrg 

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569166">POINTL</a> structure that defines the brush origin for both brushes.


### -param mix 

The foreground and background raster operations (mix modes) for <i>pboFore</i>. 


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
The <code>IPrintOemUni::TextOutAsBitmap</code> method is called from Unidrv's <a href="https://msdn.microsoft.com/library/windows/hardware/ff553132">IPrintOemDriverUni::DrvUniTextOut</a> method, if that method cannot create the text string using downloadable fonts, either because the font is not available or is rotated. <code>IPrintOemUni::TextOutAsBitmap</code> should create a bitmap image of the text and send it to the print device.

The <code>IPrintOemUni::TextOutAsBitmap</code> method is optional. If a rendering plug-in implements this method, the plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554253">IPrintOemUni::GetImplementedMethod</a> method must return S_OK when it receives "TextOutAsBitmap" as input.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553132">IPrintOemDriverUni::DrvUniTextOut</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554253">IPrintOemUni::GetImplementedMethod</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemUni::TextOutAsBitmap method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

