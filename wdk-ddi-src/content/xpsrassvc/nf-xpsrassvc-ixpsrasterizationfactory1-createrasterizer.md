---
UID: NF:xpsrassvc.IXpsRasterizationFactory1.CreateRasterizer
title: IXpsRasterizationFactory1::CreateRasterizer (xpsrassvc.h)
description: The CreateRasterize method creates an XPS rasterizer object that can handle high precision colors.
old-location: print\xpsrasterizationfactory1_createrasterizer1.htm
tech.root: print
ms.assetid: 00F1C6B7-9AD8-4E42-B433-4BD73E85CFA3
ms.date: 04/20/2018
ms.keywords: CreateRasterizer, CreateRasterizer method [Print Devices], CreateRasterizer method [Print Devices],IXPSRasterizationFactory1 interface, IXPSRasterizationFactory1 interface [Print Devices],CreateRasterizer method, IXPSRasterizationFactory1::CreateRasterizer, IXpsRasterizationFactory1.CreateRasterizer, IXpsRasterizationFactory1::CreateRasterizer, print.xpsrasterizationfactory1_createrasterizer1, xpsrassvc/IXPSRasterizationFactory1::CreateRasterizer
ms.topic: method
f1_keywords:
 - "xpsrassvc/IXPSRasterizationFactory1.CreateRasterizer"
req.header: xpsrassvc.h
req.include-header: Xpsrassvc.h
req.target-type: Windows
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
- xpsrassvc.h
api_name:
- IXPSRasterizationFactory1.CreateRasterizer
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IXpsRasterizationFactory1::CreateRasterizer


## -description


The <code>CreateRasterize</code> method creates an XPS rasterizer object that can handle high precision colors.


## -parameters




### -param xpsPage [in, optional]

Pointer to an <b>IXpsOMPage</b> object that represents the XPS fixed page to render. This object encapsulates a FixedPage section from an XPS document. For more information about <b>IXpsOMPage</b>, see <a href="https://go.microsoft.com/fwlink/p/?linkid=146349">IXpsOMPage</a><u>.</u>


### -param DPI [in]

Dots per inch in the rasterized output. This parameter applies to both the x and y dimensions of the output bitmap. The <i>DPI</i> value is the resolution of the device that is to print or display the XPS fixed page.


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

### -param pixelFormat




### -param ppIXPSRasterizer [out, optional]

This parameter points to a location into which the method writes a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/xpsrassvc/nn-xpsrassvc-ixpsrasterizer">IXpsRasterizer</a> interface of the newly created XPS rasterizer object. If the method fails, it writes <b>NULL</b> to this location and returns an error code.


#### - xpsRasPixelFormat [in]

Allows a caller to select the pixel format used by the IWICBitmap returned by the method <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/xpsrassvc/nf-xpsrassvc-ixpsrasterizer-rasterizerect">IXpsRasterizer::RasterizeRect</a>. Set this parameter to one of the following <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/xpsrassvc/ne-xpsrassvc-__midl___midl_itf_xpsrassvc_0000_0003_0001">XPSRAS_PIXEL_FORMAT</a> enumeration values:

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

## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/xpsrassvc/nn-xpsrassvc-ixpsrasterizationfactory1">XPSRasterizationFactory1</a>
 

 

