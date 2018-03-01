---
UID: NF:xpsrassvc.IXpsRasterizer.SetMinimalLineWidth
title: IXpsRasterizer::SetMinimalLineWidth method
author: windows-driver-content
description: The SetMinimalLineWidth method allows the caller to set the minimum thickness (in pixels) of the lines that the device can render.
old-location: print\ixpsrasterizer_setminimallinewidth.htm
old-project: print
ms.assetid: daf84d1a-d499-4a6e-be87-39fd16f3d87d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IXpsRasterizer, IXpsRasterizer interface [Print Devices], SetMinimalLineWidth method, IXpsRasterizer::SetMinimalLineWidth, SetMinimalLineWidth method [Print Devices], SetMinimalLineWidth method [Print Devices], IXpsRasterizer interface, SetMinimalLineWidth,IXpsRasterizer.SetMinimalLineWidth, print.ixpsrasterizer_setminimallinewidth, print_xpsrast_2208b605-31bd-4ab9-8bd5-6941a921ff7a.xml, xpsrassvc/IXpsRasterizer::SetMinimalLineWidth
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
req.lib: xpsrassvc.h
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
req.typenames: XPSRAS_BACKGROUND_COLOR
req.product: Windows 10 or later.
---

# IXpsRasterizer::SetMinimalLineWidth method


## -description


The <code>SetMinimalLineWidth</code> method allows the caller to set the minimum thickness (in pixels) of the lines that the device can render. The default minimum thickness value is 1 pixel if <code>SetMinimalLineWidth</code> is not called. This minimum thickness value only applies to the Nominal Width Stroke as defined in the XPS Specification v1.0,  Sec 11.6.12. <b>IXpsRasterizer</b> requires that any Nominal Width Stroke is rasterized with either the width specified by its <b>StrokeThickness</b> attribute, or the pixel value set by <code>SetMinimalLineWidth</code> (1 pixel if <code>SetMinimalLineWidth</code> is not called), whichever is bigger.


## -syntax


````
HRESULT STDMETHODCALLTYPE SetMinimalLineWidth(
  [in] INT width
);
````


## -parameters




### -param width [in]

The minimum thickness (in pixels) of the lines the device is capable of rendering. The value should be greater than 1.


## -returns



<code>SetMinimalLineWidth</code> always returns S_OK.




## -remarks



This method is supported in Windows 7 and later. It is not supported in versions of the Windows operating system before Windows 7.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556350">IXpsRasterizationFactory::CreateRasterizer</a>



<a href="http://msdn.microsoft.com/en-us/library/windows/desktop/ee719675.aspx">IWICBitmap</a>



<a href="..\xpsrassvc\nn-xpsrassvc-ixpsrasterizer.md">IXpsRasterizer</a>



<a href="..\xpsrassvc\nn-xpsrassvc-ixpsrasterizernotificationcallback.md">IXpsRasterizerNotificationCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556365">IXpsRasterizer::RasterizeRect</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IXpsRasterizer::SetMinimalLineWidth method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

