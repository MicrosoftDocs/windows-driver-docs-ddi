---
UID: NF:xpsrassvc.IXpsRasterizationFactory2.CreateRasterizer
title: IXpsRasterizationFactory2::CreateRasterizer
author: windows-driver-content
description: The CreateRasterizer method creates an XPS rasterizer object that can convert content from XPS to PWG Raster using the XPS Rasterization Service. PWG Raster supports non-square DPIs.
old-location: print\ixpsrasterizationfactory2_createrasterizer.htm
old-project: print
ms.assetid: C31681A0-17C6-4255-9068-7486A2101AB7
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: CreateRasterizer, CreateRasterizer method [Print Devices], CreateRasterizer method [Print Devices],IXpsRasterizationFactory2 interface, IXpsRasterizationFactory2 interface [Print Devices],CreateRasterizer method, IXpsRasterizationFactory2.CreateRasterizer, IXpsRasterizationFactory2::CreateRasterizer, print.ixpsrasterizationfactory2_createrasterizer, xpsrassvc/IXpsRasterizationFactory2::CreateRasterizer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: xpsrassvc.h
req.include-header: Xpsrassvc.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
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
-	xpsrassvc.h
api_name:
-	IXpsRasterizationFactory2.CreateRasterizer
product: Windows
targetos: Windows
req.typenames: 
---

# IXpsRasterizationFactory2::CreateRasterizer


## -description


The <b>CreateRasterizer</b> method creates an XPS rasterizer object that can convert content from XPS to PWG Raster using the <a href="https://msdn.microsoft.com/a0493b5f-d6f7-4f69-9c6e-e112c29250c9">XPS Rasterization Service</a>. PWG Raster supports non-square DPIs.



## -parameters




### -param xpsPage




### -param DPIX




### -param DPIY




### -param nonTextRenderingMode [in]

Rendering mode for nontext items in the rasterized output. This parameter indicates whether to generate antialiased output. Set this parameter to one of the following <a href="https://msdn.microsoft.com/library/windows/hardware/ff564291">XPSRAS_RENDERING_MODE</a> enumeration values:

<ul>
<li>
XPSRAS_RENDERING_MODE_ANTIALIASED

</li>
<li>
XPSRAS_RENDERING_MODE_ALIASED

</li>
</ul>

### -param textRenderingMode [in]

Rendering mode for text in the rasterized output. This parameter indicates whether to generate antialiased output. Set this parameter to one of the following XPSRAS_RENDERING_MODE enumeration values:

<ul>
<li>
XPSRAS_RENDERING_MODE_ANTIALIASED

</li>
<li>
XPSRAS_RENDERING_MODE_ALIASED

</li>
</ul>

### -param pixelFormat [in]

Allows a caller to select the pixel format used by the IWICBitmap returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff556365">IXpsRasterizer::RasterizeRect</a>. Set this parameter to one of the following <a href="https://msdn.microsoft.com/library/windows/hardware/hh802469">XPSRAS_PIXEL_FORMAT</a> enumeration values:

<ul>
<li>
XPSRAS_PIXEL_FORMAT_32BPP_PBGRA_UINT_SRGB

</li>
<li>
XPSRAS_PIXEL_FORMAT_64BPP_PRGBA_HALF_SCRGB

</li>
<li>
XPSRAS_PIXEL_FORMAT_128BPP_PRGBA_FLOAT_SCRGB

</li>
</ul>

### -param backgroundColor [in]

Allows a caller to select background color. Set this parameter to one of the following <a href="https://msdn.microsoft.com/library/windows/hardware/dn897481">XPSRAS_BACKGROUND_COLOR</a> enumeration values:

<ul>
<li>
XPSRAS_BACKGROUND_COLOR_TRANSPARENT

</li>
<li>
XPSRAS_BACKGROUND_COLOR_OPAQUE

</li>
</ul>
The default background color is XPSRAS_BACKGROUND_COLOR_TRANSPARENT.


### -param ppIXpsRasterizer






#### - **ppIXpsRasterizer [out, optional]

This parameter points to a location into which the method writes a pointer to the <a href="https://msdn.microsoft.com/1ef99120-2b3b-45aa-bcf7-16bcb9656089">IXpsRasterizer</a> interface of the newly created XPS rasterizer object. If the method fails, it writes <b>NULL</b> to this location and returns an error code.



#### - *xpsPage [in, optional]

Pointer to an <b>IXpsOMPage</b> object that represents the XPS fixed page to render. This object encapsulates a FixedPage section from an XPS document. 


#### - dpiX [in]

Dots per inch which is applied to x dimension of the rasterized output bitmap. The DPI value is the resolution of the device that is to print or display the XPS fixed page.


#### - dpiY [in]

Dots per inch which is applied to y dimension of the rasterized output bitmap.


## -returns



If this method succeeds, it returns <b>S_OK</b>. Otherwise, it returns an <b>HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn937110">IXpsRasterizationFactory2</a>
 

 

