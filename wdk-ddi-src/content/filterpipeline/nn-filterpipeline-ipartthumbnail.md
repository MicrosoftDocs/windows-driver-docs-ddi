---
UID: NN:filterpipeline.IPartThumbnail
title: IPartThumbnail (filterpipeline.h)
description: The IPartThumbnail interface is an abstraction for thumbnails in an XPS document.
old-location: print\ipartthumbnail.htm
tech.root: print
ms.assetid: 2a651a3b-1a5b-4186-9cab-38d9055b8944
ms.date: 04/20/2018
ms.keywords: IPartThumbnail, IPartThumbnail interface [Print Devices], IPartThumbnail interface [Print Devices],described, filterpipeline/IPartThumbnail, filterpipeline_56710e0f-b3df-44e6-85a5-bd155284531f.xml, print.ipartthumbnail
ms.topic: interface
f1_keywords:
 - "filterpipeline/IPartThumbnail"
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
- IPartThumbnail
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPartThumbnail interface


## -description


The <b>IPartThumbnail</b> interface is an abstraction for thumbnails in an XPS document.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPartThumbnail</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nn-filterpipeline-ipartbase">IPartBase</a>. <b>IPartThumbnail</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPartThumbnail</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ipartthumbnail-getthumbnailproperties">IPartThumbnail::GetThumbnailProperties</a>
</td>
<td align="left" width="63%">
The <b>GetThumbnailProperties</b> method gets the thumbnail properties.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ipartthumbnail-setthumbnailcontent">IPartThumbnail::SetThumbnailContent</a>
</td>
<td align="left" width="63%">
The <b>SetThumbnailContent</b> method sets the thumbnail content for the part.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nn-filterpipeline-ipartbase">IPartBase</a>
 

 

