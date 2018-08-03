---
UID: NF:prcomoem.IPrintOemUni.ImageProcessing
title: IPrintOemUni::ImageProcessing
author: windows-driver-content
description: The IPrintOemUni::ImageProcessing method can be used with Unidrv-supported printers to modify image bitmap data, in order to perform color formatting or halftoning.
old-location: print\iprintoemuni_imageprocessing.htm
tech.root: print
ms.assetid: 201450cb-cda6-4dd3-93ee-056d1627b00d
ms.author: windowsdriverdev
ms.date: 07/03/2018
ms.keywords: IPrintOemUni interface [Print Devices],ImageProcessing method, IPrintOemUni.ImageProcessing, IPrintOemUni::ImageProcessing, ImageProcessing, ImageProcessing method [Print Devices], ImageProcessing method [Print Devices],IPrintOemUni interface, prcomoem/IPrintOemUni::ImageProcessing, print.iprintoemuni_imageprocessing, print_unidrv-pscript_rendering_7b1177ff-0077-4bee-9469-7825f42323eb.xml
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
-	IPrintOemUni.ImageProcessing
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUni::ImageProcessing


## -description


The <code>IPrintOemUni::ImageProcessing</code> method can be used with Unidrv-supported printers to modify image bitmap data, in order to perform color formatting or halftoning. The method can return the modified bitmap to Unidrv or send it directly to the print spooler.


## -parameters




### -param pdevobj

Caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547573">DEVOBJ</a> structure.


### -param pSrcBitmap

Caller-supplied pointer to an input <a href="https://msdn.microsoft.com/86688b5d-575d-42e1-9158-7ffba1aaf1d3">DIB</a>.


### -param pBitmapInfoHeader

Caller-supplied pointer to a BITMAPINFOHEADER structure that describes the bitmap pointed to by <i>pSrcBitmap</i>. The BITMAPINFOHEADER structure is described in the Microsoft Windows SDK documentation.


### -param pColorTable

Caller-supplied pointer to a color table. This parameter is used only if the output format is eight bits per pixel. For more information, see the following Remarks section.

When interpreting a bitmap, you must examine the color table. Unidrv can modify the colors in a bitmap, but it will also make corresponding adjustments in the color table, resulting in no net change. However, if you ignore color table changes, and examine only the bitmap, an image might not print properly. For an example, see the discussion of the <i>pPaletteEntry</i> parameter in <a href="https://msdn.microsoft.com/library/windows/hardware/ff567320">HT_Get8BPPMaskPalette</a>.


### -param dwCallbackID

Caller-supplied value assigned to the *<b>IPCallbackID</b> attribute of the currently selected option for the ColorMode feature. For more information, see the following Remarks section.


### -param pIPParams

Caller-supplied pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551953">IPPARAMS</a> structure.


### -param ppbResult [out]

Pointer to a memory location that contains the address of a buffer. The contents of the buffer depend on where the converted DIB should be sent.

If this method intends to send the converted DIB back to Unidrv and is successful in the conversion, it should set *<i>ppbResult</i> to the address of the buffer containing the converted DIB, and should return S_OK. If the conversion fails, the method should set *<i>ppbResult</i> to <b>NULL</b>, and should return E_FAIL.

If this method intends to send the converted DIB to the spooler and is successful in the conversion, the method should set *<i>ppbResult</i>  to <b>TRUE</b>, and should return S_OK. If the conversion fails, the method should set *<i>ppbResult</i> to <b>FALSE</b> and should return E_FAIL. For more information, see the discussion of the *<b>DevBPP</b> and *<b>DevNumOfPlanes</b> attributes in the Remarks section.


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
 

<h2><a id="ddk_iprintoemuni_imageprocessing_gg"></a><a id="DDK_IPRINTOEMUNI_IMAGEPROCESSING_GG"></a></h2>
<h3><a id="source_bitmap_characteristics"></a><a id="SOURCE_BITMAP_CHARACTERISTICS"></a>Source Bitmap Characteristics</h3>
<h3><a id="destination_bitmap_characteristics"></a><a id="DESTINATION_BITMAP_CHARACTERISTICS"></a>Destination Bitmap Characteristics</h3>



## -remarks



The <code>IPrintOemUni::ImageProcessing</code> method is used to modify image bitmaps before they are sent to the print spooler. Its purpose is to provide customized support for color modes and halftoning methods not supported by Unidrv. A printer driver that sends a bitmap to the print spooler (as opposed to sending it back to Unidrv) must set the *DevBPP and *DevNumOfPlanes attributes to zero in the printer's <a href="https://msdn.microsoft.com/f67c673d-c6f0-49f0-850a-d8b00e99ddd4">GPD</a> file.

If the method is implemented, and if the GPD file entry for the current color format contains an *<b>IPCallbackID</b> attribute, Unidrv calls the method each time a bitmap is available. The call is made after GDI renders the bitmap, which is then sent to the spooler. (For information about the *<b>IPCallbackID</b> attribute, see <a href="https://msdn.microsoft.com/e6f68a50-f044-406e-b92c-8449d126bceb">Option Attributes for the ColorMode Feature</a>.)

If the current color mode, as specified by <i>dwCallbackID</i>, is one that Unidrv supports, then the <code>IPrintOemUni::ImageProcessing</code> method should perform halftoning operations on the received bitmap and return it to Unidrv for spooling. If the current color mode is one that Unidrv does not support, the method must perform halftoning operations and then spool the bitmap.

If the method is performing only halftoning operations, it must do the following:

<ul>
<li>
Perform halftoning operations on the data, as indicated by the <b>pHalftoneOption</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551953">IPPARAMS</a> structure.

</li>
<li>
Return the modified image data to Unidrv by placing it in a buffer and supplying the buffer's address as the method's return value. The returned buffer can be the one pointed to by <i>pSrcBitmap</i>, or it can be one that is locally allocated.

</li>
</ul>
For more information about customizing halftoning operations in Unidrv, see <a href="https://msdn.microsoft.com/cc14ff92-743b-42ca-b70f-0df768762f01">Customized Halftoning</a>.

To handle customized color formatting, the <code>IPrintOemUni::ImageProcessing</code> method must do the following:

<ul>
<li>
Convert DIB data, described by the <i>pSrcBitmap</i> and <i>pBitmapInfoHeader</i> parameter values, into the color format indicated by <i>dwCallbackID</i>.

</li>
<li>
Perform halftoning operations on the data, as indicated by the <b>pHalftoneOption</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551953">IPPARAMS</a> structure.

</li>
<li>
Send the data to the print spooler by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553138">IPrintOemDriverUni::DrvWriteSpoolBuf</a> method.

</li>
<li>
Modify the printer's cursor position by making appropriate calls to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553141">IPrintOemDriverUni::DrvXMoveTo</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff553144">IPrintOemDriverUni::DrvYMoveTo</a> methods.

</li>
</ul>
For more information about customizing color formatting operations in Unidrv, see <a href="https://msdn.microsoft.com/309d33e8-6338-4c32-8e03-d6cbf3371e16">Customized Color Formats</a>.

The <i>dwCallbackID</i> parameter indicates the type of color formatting, if any, that should be performed. Within the printer's GPD file, each *Option entry for the ColorMode feature describes a color format. If the format requires processing by the <code>IPrintOemUni::ImageProcessing</code> method, its *Option entry must contain an *<b>IPCallbackID</b> attribute. When Unidrv calls the <code>IPrintOemUni::ImageProcessing</code> method, it supplies the attribute value associated with the currently selected option for the ColorMode feature. This value is the <i>dwCallbackID</i> parameter's value.

Whether the <code>IPrintOemUni::ImageProcessing</code> method is performing color formatting operations and spooling image data, or just performing halftoning operations and returning processed bitmaps to Unidrv, it should export an <a href="https://msdn.microsoft.com/library/windows/hardware/ff554264">IPrintOemUni::MemoryUsage</a> method if it allocates significant amounts of memory for destination bitmaps or other purposes. Otherwise, system performance might be degraded.

If the method is implemented, it is called for every raster region on the page. However, if a region is blank, the <b>bBlankBand</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551953">IPPARAMS</a> structure is set to <b>TRUE</b>, which indicates the block is blank and the data is invalid. Because a band can be broken up into alternating blocks of blank and nonblank regions to optimize performance, the block size does not always correspond to the band size.

The source bitmap described by <i>pSrcBitmap</i> and <i>pBitmapInfoHeader</i> has the following characteristics:

<ul>
<li>
DIB contents are top-down ordered and uncompressed.

</li>
<li>
The data format is one that is listed in <a href="https://msdn.microsoft.com/4d0faba6-1994-474f-a5d3-e25cd2800cf7">Handling Color Formats</a>.

</li>
<li>
If the format requires a color table, the table is pointed to by <i>pColorTable</i>.

</li>
<li>
Color data is in PRIMARY_ORDER_CBA format, as explained in the description of the <b>ulPrimaryOrder</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566484">GDIINFO</a> structure. In other words, if the color format is RGB or CMY, the least significant <i>n</i> bits must contain the blue or yellow value, the next <i>n</i> bits must contain the green or magenta value, and the next <i>n</i> bits must contain the red or cyan value. Unused bits are in the most significant position. If the format uses 4 bits per pixel, then <i>n</i> is 1. For 24 bits per pixel, <i>n</i> is 8, as shown in the following figure. For CYMK, the fourth group of <i>n</i> bits contains black.

</li>
</ul>
<br>
<img alt="PRIMARY_ORDER_CBA Format" src="images/bitmap.png"/>
<br>
The preceding figure depicts color data in PRIMARY_ORDER_CBA format for two pixels, with 24 bits of color data per pixel. Moving from low memory addresses to high memory addresses, there are eight bits of blue data, then eight bits of green data, and then eight bits of red data, after which the pattern repeats. This is also known as BGR device output order. 
<br>
For halftoning operations, in which a processed bitmap is returned to Unidrv, the returned bitmap must have the following characteristics:
<ul>
<li>
DIB contents must be top-down ordered and uncompressed.

</li>
<li>
The data format must be one that is listed in <a href="https://msdn.microsoft.com/4d0faba6-1994-474f-a5d3-e25cd2800cf7">Handling Color Formats</a>, and it must be compatible with the *<b>DevBPP</b> and *<b>DevNumOfPlanes</b> attributes of the color format identified by <i>dwCallbackID</i>. (For information about these attributes, see <a href="https://msdn.microsoft.com/e6f68a50-f044-406e-b92c-8449d126bceb">Option Attributes for the ColorMode Feature</a>.)

</li>
<li>
If the format requires a color table, the table must be created and its address must be returned in <i>pColorTable</i>.

</li>
<li>
Color data must be returned in PRIMARY_ORDER_CBA format, as described for the source bitmap.

</li>
<li>
The BITMAPINFOHEADER structure specified by <i>pBitmapInfoHeader</i> must describe both the input and output bitmaps. The <code>IPrintOemUni::ImageProcessing</code> method must not change the structure's contents.

</li>
</ul>
The <code>IPrintOemUni::ImageProcessing</code> method is optional. If a rendering plug-in implements this method, the plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554253">IPrintOemUni::GetImplementedMethod</a> method must return S_OK when it receives "ImageProcessing" as input.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567320">HT_Get8BPPMaskPalette</a>



<a href="https://msdn.microsoft.com/097366a0-2ded-435c-9b63-2b736b716032">IPrintOemUni</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554252">IPrintOemUni::FilterGraphics</a>
 

 

