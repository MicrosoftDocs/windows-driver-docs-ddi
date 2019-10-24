---
UID: NF:xpsrassvc.IXpsRasterizer.SetMinimalLineWidth
title: IXpsRasterizer::SetMinimalLineWidth (xpsrassvc.h)
description: The SetMinimalLineWidth method allows the caller to set the minimum thickness (in pixels) of the lines that the device can render.
old-location: print\ixpsrasterizer_setminimallinewidth.htm
tech.root: print
ms.assetid: daf84d1a-d499-4a6e-be87-39fd16f3d87d
ms.date: 04/20/2018
ms.keywords: IXpsRasterizer interface [Print Devices],SetMinimalLineWidth method, IXpsRasterizer.SetMinimalLineWidth, IXpsRasterizer::SetMinimalLineWidth, SetMinimalLineWidth, SetMinimalLineWidth method [Print Devices], SetMinimalLineWidth method [Print Devices],IXpsRasterizer interface, print.ixpsrasterizer_setminimallinewidth, print_xpsrast_2208b605-31bd-4ab9-8bd5-6941a921ff7a.xml, xpsrassvc/IXpsRasterizer::SetMinimalLineWidth
ms.topic: method
f1_keywords:
 - "xpsrassvc/IXpsRasterizer.SetMinimalLineWidth"
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
- IXpsRasterizer.SetMinimalLineWidth
product:
- Windows
targetos: Windows
req.typenames: 
---

# IXpsRasterizer::SetMinimalLineWidth


## -description


The <code>SetMinimalLineWidth</code> method allows the caller to set the minimum thickness (in pixels) of the lines that the device can render. The default minimum thickness value is 1 pixel if <code>SetMinimalLineWidth</code> is not called. This minimum thickness value only applies to the Nominal Width Stroke as defined in the XPS Specification v1.0,  Sec 11.6.12. <b>IXpsRasterizer</b> requires that any Nominal Width Stroke is rasterized with either the width specified by its <b>StrokeThickness</b> attribute, or the pixel value set by <code>SetMinimalLineWidth</code> (1 pixel if <code>SetMinimalLineWidth</code> is not called), whichever is bigger.


## -parameters




### -param width [in]

The minimum thickness (in pixels) of the lines the device is capable of rendering. The value should be greater than 1.


## -returns



<code>SetMinimalLineWidth</code> always returns S_OK.




## -remarks



This method is supported in Windows 7 and later. It is not supported in versions of the Windows operating system before Windows 7.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/wincodec/nn-wincodec-iwicbitmap">IWICBitmap</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/xpsrassvc/nf-xpsrassvc-ixpsrasterizationfactory-createrasterizer">IXpsRasterizationFactory::CreateRasterizer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/xpsrassvc/nn-xpsrassvc-ixpsrasterizer">IXpsRasterizer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/xpsrassvc/nf-xpsrassvc-ixpsrasterizer-rasterizerect">IXpsRasterizer::RasterizeRect</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/xpsrassvc/nn-xpsrassvc-ixpsrasterizernotificationcallback">IXpsRasterizerNotificationCallback</a>
 

 

