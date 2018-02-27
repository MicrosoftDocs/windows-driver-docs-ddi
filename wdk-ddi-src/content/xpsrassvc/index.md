---
UID: NA:xpsrassvc
ms.assetid: 333d36bb-cab5-375c-9e40-5fba63531711
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Xpsrassvc.h header



This header is used by print. For more information, see
- [print](../_print/index.md)

Xpsrassvc.h contain these programming interfaces:


## Enumerations

| Title   | Description   |
| ---- |:---- |
| [__MIDL___MIDL_itf_xpsrassvc_0000_0001_0001 enumeration](ne-xpsrassvc-__midl___midl_itf_xpsrassvc_0000_0001_0001.md) | The XPSRAS_RENDERING_MODE enumeration specifies the rendering mode to be used by an XPS rasterizer. |
| [__MIDL___MIDL_itf_xpsrassvc_0000_0003_0001 enumeration](ne-xpsrassvc-__midl___midl_itf_xpsrassvc_0000_0003_0001.md) | XPSRAS_PIXEL_FORMAT allows a caller to select the pixel format used by the IWICBitmap interface that is returned by the IXpsRasterizer |
| [__MIDL___MIDL_itf_xpsrassvc_0000_0004_0001 enumeration](ne-xpsrassvc-__midl___midl_itf_xpsrassvc_0000_0004_0001.md) | XPSRAS_BACKGROUND_COLOR specifies the background clear color to be used by an XPS rasterizer |

## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IXpsRasterizationFactory interface](nn-xpsrassvc-ixpsrasterizationfactory.md) | The IXpsRasterizationFactory interface represents an object factory for creating XPS rasterizer objects. |
| [IXpsRasterizationFactory1 interface](nn-xpsrassvc-ixpsrasterizationfactory1.md) | In Windows 8, the improvement of XPSRas to handle high precision colors has led to the development of a new interface, IXPSRasterizationFactory1. |
| [IXpsRasterizationFactory2 interface](nn-xpsrassvc-ixpsrasterizationfactory2.md) | In Windows 10, the IXpsRasterizationFactory2 interface represents an object factory for creating components that can convert content from XPS to PWG Raster using the XPS Rasterization Service. PWG Raster supports non-square DPIs. |
| [IXpsRasterizer interface](nn-xpsrassvc-ixpsrasterizer.md) | The IXpsRasterizer interface represents an XPS rasterizer that can create a bitmap image of an XPS fixed page or of a rectangular region of a fixed page. |
| [IXpsRasterizerNotificationCallback interface](nn-xpsrassvc-ixpsrasterizernotificationcallback.md) | The IXpsRasterizerNotificationCallback interface enables the XPS rasterization service to determine whether to continue a rasterization operation that was previously initiated by an XPSDrv filter. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [IXpsRasterizationFactory2::CreateRasterizer method](nf-xpsrassvc-ixpsrasterizationfactory2-createrasterizer.md) | The CreateRasterizer method creates an XPS rasterizer object that can convert content from XPS to PWG Raster using the XPS Rasterization Service. PWG Raster supports non-square DPIs. |
| [IXpsRasterizationFactory::CreateRasterizer method](nf-xpsrassvc-ixpsrasterizationfactory-createrasterizer.md) | The CreateRasterize method creates an XPS rasterizer object. |
| [IXpsRasterizer::RasterizeRect method](nf-xpsrassvc-ixpsrasterizer-rasterizerect.md) | The RasterizeRect method rasterizes an axis-aligned, rectangular region of an XPS fixed page. |
| [IXpsRasterizer::SetMinimalLineWidth method](nf-xpsrassvc-ixpsrasterizer-setminimallinewidth.md) | The SetMinimalLineWidth method allows the caller to set the minimum thickness (in pixels) of the lines that the device can render. |
| [IXpsRasterizerNotificationCallback::Continue method](nf-xpsrassvc-ixpsrasterizernotificationcallback-continue.md) | The Continue method tells the caller (the XPS rasterization service) whether to continue rasterizing the current XPS fixed page. |
