---
UID: NN:xpsrassvc.IXpsRasterizer
title: IXpsRasterizer (xpsrassvc.h)
description: The IXpsRasterizer interface represents an XPS rasterizer that can create a bitmap image of an XPS fixed page or of a rectangular region of a fixed page.
old-location: print\ixpsrasterizer_interface.htm
tech.root: print
ms.assetid: 1ef99120-2b3b-45aa-bcf7-16bcb9656089
ms.date: 04/20/2018
ms.keywords: IXpsRasterizer, IXpsRasterizer interface [Print Devices], IXpsRasterizer interface [Print Devices],described, print.ixpsrasterizer_interface, print_xpsrast_e8c45bd1-2f79-4e4f-b6c4-034c703ff173.xml, xpsrassvc/IXpsRasterizer
ms.topic: interface
f1_keywords:
 - "xpsrassvc/IXpsRasterizer"
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
- IXpsRasterizer
product:
- Windows
targetos: Windows
req.typenames: 
---

# IXpsRasterizer interface


## -description


The <b>IXpsRasterizer</b> interface represents an XPS rasterizer that can create a bitmap image of an XPS fixed page or of a rectangular region of a fixed page.

A client obtains an <b>IXpsRasterizer</b> interface instance by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/xpsrassvc/nf-xpsrassvc-ixpsrasterizationfactory-createrasterizer">IXpsRasterizationFactory::CreateRasterizer</a> method.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IXpsRasterizer</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IXpsRasterizer</b> also has these types of members:
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
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/xpsrassvc/nf-xpsrassvc-ixpsrasterizer-rasterizerect">RasterizeRect</a>
</td>
<td align="left" width="63%">
The <code>RasterizeRect</code> method rasterizes an axis-aligned, rectangular region of an XPS fixed page.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/xpsrassvc/nf-xpsrassvc-ixpsrasterizer-setminimallinewidth">SetMinimalLineWidth</a>
</td>
<td align="left" width="63%">
The <code>SetMinimalLineWidth</code> method allows the caller to set the minimum thickness (in pixels) of the lines that the device can render. The default minimum thickness value is 1 pixel if <code>SetMinimalLineWidth</code> is not called. This minimum thickness value only applies to the Nominal Width Stroke as defined in the XPS Specification v1.0,  Sec 11.6.12. <b>IXpsRasterizer</b> requires that any Nominal Width Stroke is rasterized with either the width specified by its <b>StrokeThickness</b> attribute, or the pixel value set by <code>SetMinimalLineWidth</code> (1 pixel if <code>SetMinimalLineWidth</code> is not called), whichever is bigger.

</td>
</tr>
</table> 

