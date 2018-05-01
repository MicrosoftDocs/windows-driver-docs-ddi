---
UID: NF:xpsrassvc.IXpsRasterizer.SetMinimalLineWidth
title: IXpsRasterizer::SetMinimalLineWidth
author: windows-driver-content
description: The SetMinimalLineWidth method allows the caller to set the minimum thickness (in pixels) of the lines that the device can render.
old-location: print\ixpsrasterizer_setminimallinewidth.htm
old-project: print
ms.assetid: daf84d1a-d499-4a6e-be87-39fd16f3d87d
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IXpsRasterizer interface [Print Devices],SetMinimalLineWidth method, IXpsRasterizer.SetMinimalLineWidth, IXpsRasterizer::SetMinimalLineWidth, SetMinimalLineWidth, SetMinimalLineWidth method [Print Devices], SetMinimalLineWidth method [Print Devices],IXpsRasterizer interface, print.ixpsrasterizer_setminimallinewidth, print_xpsrast_2208b605-31bd-4ab9-8bd5-6941a921ff7a.xml, xpsrassvc/IXpsRasterizer::SetMinimalLineWidth
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	xpsrassvc.h
api_name:
-	IXpsRasterizer.SetMinimalLineWidth
product: Windows
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




<a href="http://msdn.microsoft.com/en-us/library/windows/desktop/ee719675.aspx">IWICBitmap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556350">IXpsRasterizationFactory::CreateRasterizer</a>



<a href="https://msdn.microsoft.com/1ef99120-2b3b-45aa-bcf7-16bcb9656089">IXpsRasterizer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556365">IXpsRasterizer::RasterizeRect</a>



<a href="https://msdn.microsoft.com/7616b5c7-a21f-4db1-923b-ebf2a039b5ec">IXpsRasterizerNotificationCallback</a>
 

 

