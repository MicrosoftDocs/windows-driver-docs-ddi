---
UID: NN:xpsrassvc.IXpsRasterizer
title: IXpsRasterizer
author: windows-driver-content
description: The IXpsRasterizer interface represents an XPS rasterizer that can create a bitmap image of an XPS fixed page or of a rectangular region of a fixed page.
old-location: print\ixpsrasterizer_interface.htm
old-project: print
ms.assetid: 1ef99120-2b3b-45aa-bcf7-16bcb9656089
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IXpsRasterizer, IXpsRasterizer interface [Print Devices], IXpsRasterizer interface [Print Devices],described, print.ixpsrasterizer_interface, print_xpsrast_e8c45bd1-2f79-4e4f-b6c4-034c703ff173.xml, xpsrassvc/IXpsRasterizer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: xpsrassvc.h
req.include-header: 
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	xpsrassvc.h
api_name:
-	IXpsRasterizer
product: Windows
targetos: Windows
req.typenames: 
---

# IXpsRasterizer interface


## -description


The <b>IXpsRasterizer</b> interface represents an XPS rasterizer that can create a bitmap image of an XPS fixed page or of a rectangular region of a fixed page.

A client obtains an <b>IXpsRasterizer</b> interface instance by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556350">IXpsRasterizationFactory::CreateRasterizer</a> method.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IXpsRasterizer</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IXpsRasterizer</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IXpsRasterizer</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/abf8dfc7-7921-4e9c-a338-ec783a01fca7">RasterizeRect</a>
</td>
<td align="left" width="63%">
The <code>RasterizeRect</code> method rasterizes an axis-aligned, rectangular region of an XPS fixed page.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/daf84d1a-d499-4a6e-be87-39fd16f3d87d">SetMinimalLineWidth</a>
</td>
<td align="left" width="63%">
The <code>SetMinimalLineWidth</code> method allows the caller to set the minimum thickness (in pixels) of the lines that the device can render. The default minimum thickness value is 1 pixel if <code>SetMinimalLineWidth</code> is not called. This minimum thickness value only applies to the Nominal Width Stroke as defined in the XPS Specification v1.0,  Sec 11.6.12. <b>IXpsRasterizer</b> requires that any Nominal Width Stroke is rasterized with either the width specified by its <b>StrokeThickness</b> attribute, or the pixel value set by <code>SetMinimalLineWidth</code> (1 pixel if <code>SetMinimalLineWidth</code> is not called), whichever is bigger.

</td>
</tr>
</table> 

