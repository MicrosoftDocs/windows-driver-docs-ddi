---
UID: NF:xpsrassvc.IXpsRasterizationFactory1.CreateRasterizer
title: IXpsRasterizationFactory1::CreateRasterizer (xpsrassvc.h)
description: The CreateRasterize method creates an XPS rasterizer object that can handle high precision colors.
old-location: print\xpsrasterizationfactory1_createrasterizer1.htm
tech.root: print
ms.date: 08/21/2020
keywords: ["IXpsRasterizationFactory1::CreateRasterizer"]
ms.keywords: CreateRasterizer, CreateRasterizer method [Print Devices], CreateRasterizer method [Print Devices],IXPSRasterizationFactory1 interface, IXPSRasterizationFactory1 interface [Print Devices],CreateRasterizer method, IXPSRasterizationFactory1::CreateRasterizer, IXpsRasterizationFactory1.CreateRasterizer, IXpsRasterizationFactory1::CreateRasterizer, print.xpsrasterizationfactory1_createrasterizer1, xpsrassvc/IXPSRasterizationFactory1::CreateRasterizer
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
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - IXpsRasterizationFactory1::CreateRasterizer
 - xpsrassvc/IXpsRasterizationFactory1::CreateRasterizer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - xpsrassvc.h
api_name:
 - IXpsRasterizationFactory1::CreateRasterizer
---

# IXpsRasterizationFactory1::CreateRasterizer


## -description

The **CreateRasterize** method creates an XPS rasterizer object that can handle high precision colors.

## -parameters

### -param xpsPage

[in, optional] Pointer to an **IXpsOMPage** object that represents the XPS fixed page to render. This object encapsulates a FixedPage section from an XPS document. For more information, see [IXpsOMPage](/windows/win32/api/xpsobjectmodel/nn-xpsobjectmodel-ixpsompage).

### -param DPI

[in] Dots per inch in the rasterized output. This parameter applies to both the x and y dimensions of the output bitmap. The *DPI* value is the resolution of the device that is to print or display the XPS fixed page.

### -param nonTextRenderingMode

[in] Rendering mode for nontext items in the rasterized output. This parameter indicates whether to generate antialiased output. Set this parameter to one of the following [XPSRAS_RENDERING_MODE](./ne-xpsrassvc-__midl___midl_itf_xpsrassvc_0000_0001_0001.md) enumeration values:

- XPSRAS_RENDERING_MODE_ANTIALIASED

- XPSRAS_RENDERING_MODE_ALIASED

### -param textRenderingMode

[in] Rendering mode for text in the rasterized output. This parameter indicates whether to generate antialiased output. Set this parameter to one of the following [XPSRAS_RENDERING_MODE](./ne-xpsrassvc-__midl___midl_itf_xpsrassvc_0000_0001_0001.md) enumeration values:

- XPSRAS_RENDERING_MODE_ANTIALIASED

- XPSRAS_RENDERING_MODE_ALIASED

### -param pixelFormat

The *pixelFormat* parameter.

### -param ppIXPSRasterizer

[out, optional] This parameter points to a location into which the method writes a pointer to the [IXpsRasterizer](./nn-xpsrassvc-ixpsrasterizer.md) interface of the newly created XPS rasterizer object. If the method fails, it writes **NULL** to this location and returns an error code.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

[IXPSRasterizationFactory1](./nn-xpsrassvc-ixpsrasterizationfactory1.md)

