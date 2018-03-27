---
UID: NN:filterpipeline.IPartThumbnail
title: IPartThumbnail
author: windows-driver-content
description: The IPartThumbnail interface is an abstraction for thumbnails in an XPS document.
old-location: print\ipartthumbnail.htm
old-project: print
ms.assetid: 2a651a3b-1a5b-4186-9cab-38d9055b8944
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPartThumbnail, IPartThumbnail interface [Print Devices], IPartThumbnail interface [Print Devices], described, filterpipeline/IPartThumbnail, filterpipeline_56710e0f-b3df-44e6-85a5-bd155284531f.xml, print.ipartthumbnail
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	filterpipeline.h
api_name:
-	IPartThumbnail
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IPartThumbnail interface


## -description


The <b>IPartThumbnail</b> interface is an abstraction for thumbnails in an XPS document.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPartThumbnail</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/ff551846">IPartBase</a>. <b>IPartThumbnail</b> also has these types of members:
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551942">IPartThumbnail::GetThumbnailProperties</a>
</td>
<td align="left" width="63%">
The <b>GetThumbnailProperties</b> method gets the thumbnail properties.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551950">IPartThumbnail::SetThumbnailContent</a>
</td>
<td align="left" width="63%">
The <b>SetThumbnailContent</b> method sets the thumbnail content for the part.

</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551846">IPartBase</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPartThumbnail interface%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

