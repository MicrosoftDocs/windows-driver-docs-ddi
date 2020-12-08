---
UID: NF:xpsrassvc.IXpsRasterizationFactory.CreateRasterizer
title: IXpsRasterizationFactory::CreateRasterizer (xpsrassvc.h)
description: The CreateRasterize method creates an XPS rasterizer object.
old-location: print\ixpsrasterizationfactory_createrasterizer.htm
tech.root: print
ms.date: 08/21/2020
keywords: ["IXpsRasterizationFactory::CreateRasterizer"]
ms.keywords: CreateRasterizer, CreateRasterizer method [Print Devices], CreateRasterizer method [Print Devices],IXpsRasterizationFactory interface, IXpsRasterizationFactory interface [Print Devices],CreateRasterizer method, IXpsRasterizationFactory.CreateRasterizer, IXpsRasterizationFactory::CreateRasterizer, print.ixpsrasterizationfactory_createrasterizer, print_xpsrast_5eddcd20-40a0-47da-8b1c-94d17902d783.xml, xpsrassvc/IXpsRasterizationFactory::CreateRasterizer
req.header: xpsrassvc.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating system.
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
 - IXpsRasterizationFactory::CreateRasterizer
 - xpsrassvc/IXpsRasterizationFactory::CreateRasterizer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - xpsrassvc.h
api_name:
 - IXpsRasterizationFactory.CreateRasterizer
---

# IXpsRasterizationFactory::CreateRasterizer


## -description

The **CreateRasterize** method creates an XPS rasterizer object.

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

[in] Rendering mode for text in the rasterized output. This parameter indicates whether to generate antialiased output. Set this parameter to one of the following XPSRAS_RENDERING_MODE enumeration values:

- XPSRAS_RENDERING_MODE_ANTIALIASED

- XPSRAS_RENDERING_MODE_ALIASED

### -param ppIXPSRasterizer

[out, optional] This parameter points to a location into which the method writes a pointer to the [IXpsRasterizer](./nn-xpsrassvc-ixpsrasterizer.md) interface of the newly created XPS rasterizer object. If the method fails, it writes **NULL** to this location and returns an error code.

## -returns

**CreateRasterizer** returns S_OK if the call was successful. Otherwise, the method returns an error code.

Possible error return values include:

| Return code | Description |
|--|--|
| E_POINTER | Parameter *xpsPage* or *ppIXPSRasterizer* is **NULL** |
| E_INVALIDARG | Parameter *nonTextRenderingMode* or *textRenderingMode* is not a valid XPSRAS_RENDERING_MODE enumeration value. |
| E_OUTOFMEMORY | Out of memory |

## -remarks

This method is supported in Windows 7 and later.

Typically, an XPSDrv filter in an XPS pipeline calls this method to obtain an XPS rasterizer. It then uses the rasterizer to rasterize the XPS fixed page encapsulated by the object to which the parameter *xpsPage* points.

The parameter *DPI* specifies the printer resolution, which is assumed to be the same in both the horizontal and vertical dimensions. The width and height of the XPS fixed page, which can be obtained from the **IXpsOMPage::GetPageDimensions** method, are expressed in 1/96-inch units. Multiply these width and height values by *DPI*/96 to determine the width and height, in pixels, of the rasterized page. For more information about **IXpsOMPage::GetPageDimensions**, see [IXpsOMPage](/windows/win32/api/xpsobjectmodel/nf-xpsobjectmodel-ixpsompage-getpagedimensions). For more information about how the XPS rasterizer object uses the DPI value, see [IXpsRasterizer::RasterizeRect](./nf-xpsrassvc-ixpsrasterizer-rasterizerect.md).

If successful, the method creates an XPS rasterizer object and passes to the caller a counted reference to the object's **IXpsRasterizer** interface. When the object is no longer needed, the caller is responsible for releasing the object by calling the [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) method on the object's **IXpsRasterizer** interface.

If the method fails and *ppIXPSRasterizer* is non-**NULL**, the method sets **ppIXPSRasterizer* = **NULL**.

For a code example that calls the **CreateRasterizer** method, see the XPSRasFilter sample in the WDK. This sample is located in the Src\Print\Xpsrasfilter folder in your WDK installation.

## -see-also

[IXpsRasterizationFactory](./nn-xpsrassvc-ixpsrasterizationfactory.md)

[IXpsRasterizer](./nn-xpsrassvc-ixpsrasterizer.md)

[IXpsRasterizer::RasterizeRect](./nf-xpsrassvc-ixpsrasterizer-rasterizerect.md)

[XPSRAS_RENDERING_MODE](./ne-xpsrassvc-__midl___midl_itf_xpsrassvc_0000_0001_0001.md)
