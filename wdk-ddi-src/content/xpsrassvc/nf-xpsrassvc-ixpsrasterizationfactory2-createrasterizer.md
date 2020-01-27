---
UID: NF:xpsrassvc.IXpsRasterizationFactory2.CreateRasterizer
title: IXpsRasterizationFactory2::CreateRasterizer (xpsrassvc.h)
description: The CreateRasterizer method creates an XPS rasterizer object that can convert content from XPS to PWG Raster using the XPS Rasterization Service. PWG Raster supports non-square DPIs.
old-location: print\ixpsrasterizationfactory2_createrasterizer.htm
tech.root: print
ms.assetid: C31681A0-17C6-4255-9068-7486A2101AB7
ms.date: 04/20/2018
ms.keywords: CreateRasterizer, CreateRasterizer method [Print Devices], CreateRasterizer method [Print Devices],IXpsRasterizationFactory2 interface, IXpsRasterizationFactory2 interface [Print Devices],CreateRasterizer method, IXpsRasterizationFactory2.CreateRasterizer, IXpsRasterizationFactory2::CreateRasterizer, print.ixpsrasterizationfactory2_createrasterizer, xpsrassvc/IXpsRasterizationFactory2::CreateRasterizer
f1_keywords:
 - "xpsrassvc/IXpsRasterizationFactory2.CreateRasterizer"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- xpsrassvc.h
api_name:
- IXpsRasterizationFactory2.CreateRasterizer
product:
- Windows
targetos: Windows
req.typenames: 
---

# IXpsRasterizationFactory2::CreateRasterizer


## -description


The <b>CreateRasterizer</b> method creates an XPS rasterizer object that can convert content from XPS to PWG Raster using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_print/index">XPS Rasterization Service</a>. PWG Raster supports non-square DPIs.



## -parameters




### -param xpsPage




### -param DPIX




### -param DPIY




### -param nonTextRenderingMode [in]

Rendering mode for nontext items in the rasterized output. This parameter indicates whether to generate antialiased output. Set this parameter to one of the following <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/xpsrassvc/ne-xpsrassvc-__midl___midl_itf_xpsrassvc_0000_0001_0001">XPSRAS_RENDERING_MODE</a> enumeration values:

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

Allows a caller to select the pixel format used by the IWICBitmap returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/xpsrassvc/nf-xpsrassvc-ixpsrasterizer-rasterizerect">IXpsRasterizer::RasterizeRect</a>. Set this parameter to one of the following <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/xpsrassvc/ne-xpsrassvc-__midl___midl_itf_xpsrassvc_0000_0003_0001">XPSRAS_PIXEL_FORMAT</a> enumeration values:

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

Allows a caller to select background color. Set this parameter to one of the following <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/xpsrassvc/ne-xpsrassvc-__midl___midl_itf_xpsrassvc_0000_0004_0001">XPSRAS_BACKGROUND_COLOR</a> enumeration values:

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

This parameter points to a location into which the method writes a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/xpsrassvc/nn-xpsrassvc-ixpsrasterizer">IXpsRasterizer</a> interface of the newly created XPS rasterizer object. If the method fails, it writes <b>NULL</b> to this location and returns an error code.



#### - *xpsPage [in, optional]

Pointer to an <b>IXpsOMPage</b> object that represents the XPS fixed page to render. This object encapsulates a FixedPage section from an XPS document. 


#### - dpiX [in]

Dots per inch which is applied to x dimension of the rasterized output bitmap. The DPI value is the resolution of the device that is to print or display the XPS fixed page.


#### - dpiY [in]

Dots per inch which is applied to y dimension of the rasterized output bitmap.


## -returns



If this method succeeds, it returns <b>S_OK</b>. Otherwise, it returns an <b>HRESULT</b> error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/xpsrassvc/nn-xpsrassvc-ixpsrasterizationfactory2">IXpsRasterizationFactory2</a>
 

 

