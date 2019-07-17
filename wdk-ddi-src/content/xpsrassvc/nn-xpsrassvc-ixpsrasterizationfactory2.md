---
UID: NN:xpsrassvc.IXpsRasterizationFactory2
title: IXpsRasterizationFactory2 (xpsrassvc.h)
description: In Windows 10, the IXpsRasterizationFactory2 interface represents an object factory for creating components that can convert content from XPS to PWG Raster using the XPS Rasterization Service. PWG Raster supports non-square DPIs.
old-location: print\ixpsrasterizationfactory2.htm
tech.root: print
ms.assetid: 23994CD9-A65B-4BD7-9070-3F575D011953
ms.date: 04/20/2018
ms.keywords: IXpsRasterizationFactory2, IXpsRasterizationFactory2 interface [Print Devices], IXpsRasterizationFactory2 interface [Print Devices],described, print.ixpsrasterizationfactory2, xpsrassvc/IXpsRasterizationFactory2
ms.topic: interface
f1_keywords:
 - "xpsrassvc/IXpsRasterizationFactory2"
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
- IXpsRasterizationFactory2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IXpsRasterizationFactory2 interface


## -description


In Windows 10, the <b>IXpsRasterizationFactory2</b> interface represents an object factory for creating components that can  convert content from XPS to PWG Raster using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_print/index">XPS Rasterization Service</a>. PWG Raster supports non-square DPIs.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IXpsRasterizationFactory2</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IXpsRasterizationFactory2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IXpsRasterizationFactory2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/xpsrassvc/nf-xpsrassvc-ixpsrasterizationfactory2-createrasterizer">CreateRasterizer</a>
</td>
<td align="left" width="63%">
The <b>CreateRasterizer</b> method creates an XPS rasterizer object that can convert content from XPS to PWG Raster using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_print/index">XPS Rasterization Service</a>. PWG Raster supports non-square DPIs.


</td>
</tr>
</table> 

