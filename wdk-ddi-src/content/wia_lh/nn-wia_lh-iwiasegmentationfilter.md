---
UID: NN:wia_lh.IWiaSegmentationFilter
title: IWiaSegmentationFilter (wia_lh.h)
description: The IWiaSegmentationFilter interface provides the DetectRegions method, which enables minidrivers to detect image subregions on a flatbed scanner's platen. This interface is available in Windows Vista and later.
old-location: image\iwiasegmentationfilter_interface.htm
tech.root: image
ms.assetid: 93f2942b-3c01-43e7-9b8a-9542ab7bfd74
ms.date: 05/03/2018
ms.keywords: IWiaSegmentationFilter, IWiaSegmentationFilter interface [Imaging Devices], IWiaSegmentationFilter interface [Imaging Devices],described, image.iwiasegmentationfilter_interface, iwiasegmentationfilter_24576c71-3e48-4152-bbd2-d3722d07a283.xml, wia_lh/IWiaSegmentationFilter
ms.topic: interface
f1_keywords:
 - "wia_lh/IWiaSegmentationFilter"
req.header: wia_lh.h
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
- wia_lh.h
api_name:
- IWiaSegmentationFilter
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaSegmentationFilter interface


## -description



The <b>IWiaSegmentationFilter</b> interface provides the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wia_lh/nf-wia_lh-iwiasegmentationfilter-detectregions">DetectRegions</a> method, which enables minidrivers to detect image subregions on a flatbed scanner's platen. This interface is available in Windows Vista and later.




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWiaSegmentationFilter</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IWiaSegmentationFilter</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWiaSegmentationFilter</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wia_lh/nf-wia_lh-iwiasegmentationfilter-detectregions">DetectRegions</a>
</td>
<td align="left" width="63%">
The <b>IWiaSegmentationFilter::DetectRegions</b> method determines the subregions of an image laid out on the flatbed platen so that each subregion can be acquired into a separate image item.

</td>
</tr>
</table> 

