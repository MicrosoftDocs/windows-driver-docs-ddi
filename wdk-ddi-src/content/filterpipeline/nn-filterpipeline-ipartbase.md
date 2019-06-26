---
UID: NN:filterpipeline.IPartBase
title: IPartBase (filterpipeline.h)
description: The IPartBase interface is a common base for document part interfaces.
old-location: print\ipartbase.htm
tech.root: print
ms.assetid: 7523990f-04de-4182-99d9-fba100bebb84
ms.date: 04/20/2018
ms.keywords: IPartBase, IPartBase interface [Print Devices], IPartBase interface [Print Devices],described, filterpipeline/IPartBase, filterpipeline_aaad898e-c110-439c-9983-fedbab82c06d.xml, print.ipartbase
ms.topic: interface
req.header: filterpipeline.h
req.include-header: Filterpipeline.h
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
- filterpipeline.h
api_name:
- IPartBase
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPartBase interface


## -description


The <b>IPartBase </b>interface is a common base for document part interfaces.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPartBase</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPartBase</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPartBase</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ipartbase-getpartcompression">IPartBase::GetPartCompression</a>
</td>
<td align="left" width="63%">
The <b>GetPartCompression</b> method gets the compression of the part.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ipartbase-getstream">IPartBase::GetStream</a>
</td>
<td align="left" width="63%">
The <b>GetStream</b> method gets the stream object that contains the part data. Each part has part-specific data that is associated with it (for example, a font, image, and page markup).

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ipartbase-geturi">IPartBase::GetUri</a>
</td>
<td align="left" width="63%">
The <b>GetUri</b> method gets the URI of the part.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ipartbase-setpartcompression">IPartBase::SetPartCompression</a>
</td>
<td align="left" width="63%">
The <b>SetPartCompression</b> method sets the compression of the part.

</td>
</tr>
</table> 

