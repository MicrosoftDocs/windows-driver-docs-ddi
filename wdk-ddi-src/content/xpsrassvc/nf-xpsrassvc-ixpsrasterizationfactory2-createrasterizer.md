---
UID: NF:xpsrassvc.IXpsRasterizationFactory2.CreateRasterizer
title: IXpsRasterizationFactory2::CreateRasterizer (xpsrassvc.h)
description: The CreateRasterizer method creates an XPS rasterizer object that can convert content from XPS to PWG Raster using the XPS Rasterization Service. PWG Raster supports non-square DPIs.
tech.root: print
ms.date: 04/19/2022
keywords: ["IXpsRasterizationFactory2::CreateRasterizer"]
ms.keywords: CreateRasterizer, CreateRasterizer method [Print Devices], CreateRasterizer method [Print Devices],IXpsRasterizationFactory2 interface, IXpsRasterizationFactory2 interface [Print Devices],CreateRasterizer method, IXpsRasterizationFactory2.CreateRasterizer, IXpsRasterizationFactory2::CreateRasterizer, print.ixpsrasterizationfactory2_createrasterizer, xpsrassvc/IXpsRasterizationFactory2::CreateRasterizer
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IXpsRasterizationFactory2::CreateRasterizer
 - xpsrassvc/IXpsRasterizationFactory2::CreateRasterizer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - xpsrassvc.h
api_name:
 - IXpsRasterizationFactory2::CreateRasterizer
---

## -description

The **CreateRasterizer** method creates an XPS rasterizer object that can convert content from XPS to PWG Raster using the [XPS Rasterization Service](/windows-hardware/drivers/ddi/_print/index). PWG Raster supports non-square DPIs.

## -parameters

### -param xpsPage [in, optional]

Pointer to an **IXpsOMPage** object that represents the XPS fixed page to render. This object encapsulates a FixedPage section from an XPS document.

### -param DPIX [in]

Dots per inch which is applied to x dimension of the rasterized output bitmap. The DPI value is the resolution of the device that is to print or display the XPS fixed page.

### -param DPIY [in]

Dots per inch which is applied to y dimension of the rasterized output bitmap.

### -param nonTextRenderingMode [in]

Rendering mode for nontext items in the rasterized output. This parameter indicates whether to generate antialiased output. Set this parameter to one of the following [XPSRAS_RENDERING_MODE](/windows-hardware/drivers/ddi/xpsrassvc/ne-xpsrassvc-__midl___midl_itf_xpsrassvc_0000_0001_0001) enumeration values:

- XPSRAS_RENDERING_MODE_ANTIALIASED

- XPSRAS_RENDERING_MODE_ALIASED

### -param textRenderingMode [in]

Rendering mode for text in the rasterized output. This parameter indicates whether to generate antialiased output. Set this parameter to one of the following XPSRAS_RENDERING_MODE enumeration values:

- XPSRAS_RENDERING_MODE_ANTIALIASED

- XPSRAS_RENDERING_MODE_ALIASED

### -param pixelFormat [in]

Allows a caller to select the pixel format used by the IWICBitmap returned by [IXpsRasterizer::RasterizeRect](/windows-hardware/drivers/ddi/xpsrassvc/nf-xpsrassvc-ixpsrasterizer-rasterizerect). Set this parameter to one of the following [XPSRAS_PIXEL_FORMAT](/windows-hardware/drivers/ddi/xpsrassvc/ne-xpsrassvc-__midl___midl_itf_xpsrassvc_0000_0003_0001) enumeration values:

- XPSRAS_PIXEL_FORMAT_32BPP_PBGRA_UINT_SRGB

- XPSRAS_PIXEL_FORMAT_64BPP_PRGBA_HALF_SCRGB

- XPSRAS_PIXEL_FORMAT_128BPP_PRGBA_FLOAT_SCRGB

### -param backgroundColor [in]

Allows a caller to select background color. Set this parameter to one of the following [XPSRAS_BACKGROUND_COLOR](/windows-hardware/drivers/ddi/xpsrassvc/ne-xpsrassvc-__midl___midl_itf_xpsrassvc_0000_0004_0001) enumeration values:

- XPSRAS_BACKGROUND_COLOR_TRANSPARENT

- XPSRAS_BACKGROUND_COLOR_OPAQUE

- The default background color is XPSRAS_BACKGROUND_COLOR_TRANSPARENT.

### -param ppIXpsRasterizer [out, optional]

This parameter points to a location into which the method writes a pointer to the [IXpsRasterizer](/windows-hardware/drivers/ddi/xpsrassvc/nn-xpsrassvc-ixpsrasterizer) interface of the newly created XPS rasterizer object. If the method fails, it writes **NULL** to this location and returns an error code.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

[IXpsRasterizationFactory2](/windows-hardware/drivers/ddi/xpsrassvc/nn-xpsrassvc-ixpsrasterizationfactory2)
