---
UID: NF:prcomoem.IPrintOemUni.FilterGraphics
title: IPrintOemUni::FilterGraphics
description: The IPrintOemUni::FilterGraphics method can be used with Unidrv-supported printers to modify scan line data and send it to the spooler.
old-location: print\iprintoemuni_filtergraphics.htm
tech.root: print
ms.assetid: a1651745-08f0-44f2-bb9f-825d6497db42
ms.date: 04/20/2018
ms.keywords: FilterGraphics, FilterGraphics method [Print Devices], FilterGraphics method [Print Devices],IPrintOemUni interface, IPrintOemUni interface [Print Devices],FilterGraphics method, IPrintOemUni.FilterGraphics, IPrintOemUni::FilterGraphics, prcomoem/IPrintOemUni::FilterGraphics, print.iprintoemuni_filtergraphics, print_unidrv-pscript_rendering_7e6c6ada-fa4a-4188-b7c2-0ac95869bcdc.xml
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
-	IPrintOemUni.FilterGraphics
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUni::FilterGraphics


## -description


The <code>IPrintOemUni::FilterGraphics</code> method can be used with Unidrv-supported printers to modify scan line data and send it to the spooler.


## -parameters




### -param pdevobj

Caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547573">DEVOBJ</a> structure.


### -param pBuf

Caller-supplied pointer to a buffer containing scan line data to be printed.


### -param dwLen

Caller-supplied value representing the length, in bytes, of the data pointed to by <i>pBuf</i>.


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



The <code>IPrintOemUni::FilterGraphics</code> method is used to modify scan line data before it is sent to the print spooler. The method is responsible for sending the data it receives to the spooler.

The <code>IPrintOemUni::FilterGraphics</code> method is optional. If a rendering plug-in implements this method, the plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554253">IPrintOemUni::GetImplementedMethod</a> method must return S_OK when it receives "FilterGraphics" as input.

If the <code>IPrintOemUni::FilterGraphics</code> method is implemented, Unidrv does not spool printer data. Instead, Unidrv calls this method each time a buffer of image data is ready to be spooled. Note that when this method is implemented, Unidrv also does not compress printer data, as it normally does. If you intend to make use of Unidrv compression, you should not implement this method. Also, you should modify <b>IPrintOemUni::GetImplementedMethod</b> so that it returns S_FALSE when it is passed the string "FilterGraphics".

The method can perform final postprocessing of image data, such as removing adjacent dots or any other data stream filtering operation that Unidrv does not provide. It must then spool the data by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553138">IPrintOemDriverUni::DrvWriteSpoolBuf</a> method.

<code>IPrintOemUni::FilterGraphics</code> method is called by Unidrv's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556281">DrvSendPage</a> function. If you want to implement <code>IPrintOemUni::FilterGraphics</code>, you must not completely override Unidrv's <b>DrvSendPage</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff556250">DrvNextBand</a> functions. 

Before Unidrv's <b>DrvSendPage</b> function calls the plug-in's <code>IPrintOemUni::FilterGraphics</code> implementation, <b>DrvSendPage</b>.

<ol>
<li>
If necessary, transposes the bitmap that is to be rendered.

</li>
<li>
Transforms an output pass that consists of color data into a single contiguous array of data.

</li>
<li>
Processes a group of scan lines and turn this data into commands for the printer.

</li>
<li>
Sets X/Y position and passes the line of graphics data to the printer.

</li>
</ol>
If the plug-in has implemented <code>IPrintOemUni::FilterGraphics,</code> Unidrv will call the plug-in with the scan line data instead of sending it to the printer.

The <code>IPrintOemUni::FilterGraphics</code> method allows a rendering plug-in to modify scan line data and send it to the spooler. If you implement this function, Unidrv will not spool your data. Instead, <code>IPrintOemUni::FilterGraphics</code> will be called every time a buffer of data is ready to be spooled and sent to the printer.

You can use <code>IPrintOemUni::FilterGraphics</code>  to implement a special compression method or to perform bit manipulation on the data stream that is sent to the printer or both. In any situation, the driver's built-in compression code is not used. <code>IPrintOemUni::FilterGraphics</code> is presented with a block of data and is required to output this data by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548662">DrvWriteSpoolBuf</a> function. The core driver (Unidrv) will perform no further processing of the raster data after calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff557725">OEMFilterGraphics</a>. 

When you implement the <code>IPrintOemUni::FilterGraphics</code> method in your plug-in, it will be used for sending the raster data directly to the printer. The number of scan lines in a block is specified through the *<b>PinsPerPhysPass</b> attribute that is associated with the <a href="https://msdn.microsoft.com/f04cd119-38c7-465c-b4fd-d657aa5bfacd">Resolution feature</a> This attribute is optional, and if you do not specify it, it is set to 1 (like it is for most of the inkjet and page printers). Otherwise, *<b>PinsPerPhysPass</b> should be a multiple of 8. In <code>IPrintOemUni::FilterGraphics</code>, the <i>pBuf</i> parameter points to the buffer that contains the scan line raster data that you will manipulate if necessary (for example, for compression) and finally send out. The <i>dwLen</i> parameter is the length of the buffer that <i>pBuf</i> points to.  

The following list describes several common scenarios for implementing <code>IPrintOemUni::FilterGraphics</code>:

<ol>
<li>
Special compression techniques

</li>
<li>
Bit manipulation of the incoming raster data before sending it out to the printer

</li>
</ol>
<code>IPrintOemUni::FilterGraphics</code> finally sends all of the data to the printer by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548662">DrvWriteSpoolBuf</a> function. The core driver (Unidrv) does not do any more processing on the data that <code>IPrintOemUni::FilterGraphics</code> sends out. If the plug-in is performing special compression or bit manipulation, the plug-in must allocate the buffers that are necessary for the special compression or bit manipulation. If the plug-in does not allocate its own buffers and if the compressed data is smaller than the source, the output will overwrite the source buffer.

The <code>IPrintOemUni::FilterGraphics</code> method gives you access to the scan line data itself and gives you the ability to post-process the raster data.

<div class="alert"><b>Note</b>    The number of scan lines is equal to the height of the image. For example, a 1 bit per pixel (bpp) thickness of each scan line is equal to the  width of 1 pixel, so the number of scan lines is equal to the height of the image.</div>
<div> </div>
For more information about customizing Unidrv's rendering operations, see <a href="https://msdn.microsoft.com/aff39531-ca40-4985-b458-c6217f8a2e5c">Unidrv-Specific Customized Rendering</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556250">DrvNextBand</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556281">DrvSendPage</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548662">DrvWriteSpoolBuf</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553138">IPrintOemDriverUni::DrvWriteSpoolBuf</a>



<a href="https://msdn.microsoft.com/097366a0-2ded-435c-9b63-2b736b716032">IPrintOemUni</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554253">IPrintOemUni::GetImplementedMethod</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554261">IPrintOemUni::ImageProcessing</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557725">OEMFilterGraphics</a>
 

 

