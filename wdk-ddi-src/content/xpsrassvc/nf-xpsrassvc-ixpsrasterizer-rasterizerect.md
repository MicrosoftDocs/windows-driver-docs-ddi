---
UID: NF:xpsrassvc.IXpsRasterizer.RasterizeRect
title: IXpsRasterizer::RasterizeRect (xpsrassvc.h)
description: The RasterizeRect method rasterizes an axis-aligned, rectangular region of an XPS fixed page.
old-location: print\ixpsrasterizer_rasterizerect.htm
tech.root: print
ms.assetid: abf8dfc7-7921-4e9c-a338-ec783a01fca7
ms.date: 04/20/2018
keywords: ["IXpsRasterizer::RasterizeRect"]
ms.keywords: IXpsRasterizer interface [Print Devices],RasterizeRect method, IXpsRasterizer.RasterizeRect, IXpsRasterizer::RasterizeRect, RasterizeRect, RasterizeRect method [Print Devices], RasterizeRect method [Print Devices],IXpsRasterizer interface, print.ixpsrasterizer_rasterizerect, print_xpsrast_de9e1518-8388-4cc4-9787-8774996221bf.xml, xpsrassvc/IXpsRasterizer::RasterizeRect
f1_keywords:
 - "xpsrassvc/IXpsRasterizer.RasterizeRect"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- xpsrassvc.h
api_name:
- IXpsRasterizer.RasterizeRect
product:
- Windows
targetos: Windows
req.typenames: 
---

# IXpsRasterizer::RasterizeRect

## -description

The **RasterizeRect** method rasterizes an axis-aligned, rectangular region of an XPS fixed page.

## -parameters

### -param x [in]

The x coordinate, in pixels, at the left edge of the output bitmap.

### -param y [in]

The y coordinate, in pixels, at the top edge of the output bitmap.

### -param width [in]

The width, in pixels, of the output bitmap.

### -param height [in]

The height, in pixels, of the output bitmap.

### -param notificationCallback [in, optional]

Pointer to the [IXpsRasterizerNotificationCallback](https://docs.microsoft.com/windows-hardware/drivers/ddi/xpsrassvc/nn-xpsrassvc-ixpsrasterizernotificationcallback) interface of a notification object that is implemented by the caller. This parameter is optional and can be **NULL** if the caller does not require notification callbacks.

### -param bitmap [out, optional]

Pointer to a location into which the method writes a pointer to the [IWICBitmap](https://docs.microsoft.com/windows/win32/api/wincodec/nn-wincodec-iwicbitmap) interface of the newly created bitmap object. If the method fails, it writes **NULL** to this location and returns an error code.

## -returns

**RasterizeRect** returns S_OK if the call was successful. Otherwise, the method returns an error code. Possible error return values include:

| Return code | Description |
| --- | --- |
| E_POINTER | Parameter *bitmap* is **NULL**. |
| E_INVALIDARG | Parameter *width* or *height* is less than or equal to 0. |

## -remarks

This method is supported in Windows 7 and later. It is not supported in versions of the Windows operating system before Windows 7.

If successful, this method creates a Windows imaging component (WIC) bitmap object and passes to the caller a counted reference to the object's [IWICBitmap](https://docs.microsoft.com/windows/win32/api/wincodec/nn-wincodec-iwicbitmap) interface. When the object is no longer needed, the caller is responsible for releasing the object by calling the [Release](https://go.microsoft.com/fwlink/p/?linkid=98433) method on the object's [IWICBitmap](https://docs.microsoft.com/windows/win32/api/wincodec/nn-wincodec-iwicbitmap) interface.

The WIC bitmap created by this method has a 32-bit pixel format that contains 8-bit red, green, and blue channels and uses the standard RGB (sRGB) color space. In addition, the format contains an 8-bit alpha component. The color components in each pixel value are pre-multiplied by the alpha component. The pixel format is specified by the GUID value **GUID_WICPixelFormat32bppPBGRA**, which is defined in the header file Wincodec.h. For more information about this format, see [Native Pixel Formats Overview](https://docs.microsoft.com/windows/win32/wic/-wic-codec-native-pixel-formats).

The [IXpsRasterizationFactory::CreateRasterizer](https://docs.microsoft.com/windows-hardware/drivers/ddi/xpsrassvc/nf-xpsrassvc-ixpsrasterizationfactory-createrasterizer) method's *DPI* parameter specifies the resolution, in dots per inch, at which the bitmap is to be rendered. As described in the [XPS specification](https://download.microsoft.com/download/1/6/a/16acc601-1b7a-42ad-8d4e-4f0aa156ec3e/XPS_1_0.exe), the width and height of a fixed page in an XPS document are specified in 1/96-inch units. To determine the dimensions (in pixels) of the bitmap required to represent the entire fixed page, multiply the width and height by *DPI*/96.

To accommodate printers that require a fixed page to be rasterized as a series of horizontal or vertical bands, parameters *x*, *y*, *width*, and *height* specify a rectangular region of the fixed page that is to be rasterized. All four parameter values are specified in pixels. Parameters *x* and *y* are the coordinates of the top, left corner of the rectangular region; they are specified as pixel displacements from the coordinate origin (0, 0). Parameters *width* and *height* are the dimensions of the rectangular region.

For example, if *w*XPS and *h*XPS are the width and height of an XPS fixed page in 1/96-inch units, **RasterizeRect** generates a bitmap representation of the bottom half of the fixed page if parameters *x*, *y*, *width*, and *height* are set to the following values:

*x*
*y*
*h*
*DPI*
*width*
*w*
*DPI*
*height*
*h*
*DPI*

If the *notificationCallback* parameter is non-**NULL**, the **RasterizeRect** method takes a counted reference to the notification object's **IXpsRasterizerNotificationCallback** interface. It does so by calling the **AddRef** method on the interface before making any calls to the **IXpsRasterizerNotificationCallback::Continue** method. Before **RasterizeRect** returns, it releases the notification object by calling the **Release** method on the **IXpsRasterizerNotificationCallback* interface.

As explained in the [XPS specification](https://download.microsoft.com/download/1/6/a/16acc601-1b7a-42ad-8d4e-4f0aa156ec3e/XPS_1_0.exe), the optional **BleedBox** attribute can specify a bleed box that extends outside the boundaries of a fixed page. To accommodate bleed boxes, the rectangle defined by the parameters *x*, *y*, *width*, and *height* can also extend beyond the boundaries of the fixed page. The method accepts any values, positive or negative, for *x* and *y*, and it accepts any positive, nonzero values for *width* and *height*. The rectangle specified by these parameters defines the clipping region for the rasterization operation. If the rectangle extends beyond the boundaries of the fixed page, the clipping region also extends beyond these boundaries.

If the method fails and *bitmap* is non-**NULL**, the method sets **bitmap* = **NULL**.

For a code example that calls the **RasterizeRect** method, see the XPSRasFilter sample in the WDK. This sample is located in the Src\Print\Xpsrasfilter folder in your WDK installation.

## -see-also

[IWICBitmap](https://docs.microsoft.com/windows/win32/api/wincodec/nn-wincodec-iwicbitmap)

[IXpsRasterizationFactory::CreateRasterizer](https://docs.microsoft.com/windows-hardware/drivers/ddi/xpsrassvc/nf-xpsrassvc-ixpsrasterizationfactory-createrasterizer)

[IXpsRasterizer](https://docs.microsoft.com/windows-hardware/drivers/ddi/xpsrassvc/nn-xpsrassvc-ixpsrasterizer)

[IXpsRasterizer::SetMinimalLineWidth](https://docs.microsoft.com/windows-hardware/drivers/ddi/xpsrassvc/nf-xpsrassvc-ixpsrasterizer-setminimallinewidth)

[IXpsRasterizerNotificationCallback](https://docs.microsoft.com/windows-hardware/drivers/ddi/xpsrassvc/nn-xpsrassvc-ixpsrasterizernotificationcallback)
