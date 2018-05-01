---
UID: NN:filterpipeline.IPartImage
title: IPartImage
author: windows-driver-content
description: The IPartImage interface is the abstraction for images in an XPS document.
old-location: print\ipartimage.htm
old-project: print
ms.assetid: 7bb39a5b-7519-47a6-82ca-440942ae2c84
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IPartImage, IPartImage interface [Print Devices], IPartImage interface [Print Devices],described, filterpipeline/IPartImage, filterpipeline_faed49d4-60d1-4063-a4aa-c9ec8c56655d.xml, print.ipartimage
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	filterpipeline.h
api_name:
-	IPartImage
product: Windows
targetos: Windows
req.typenames: 
---

# IPartImage interface


## -description


The <b>IPartImage</b> interface is the abstraction for images in an XPS document.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPartImage</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/ff551846">IPartBase</a>. <b>IPartImage</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPartImage</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551911">IPartImage::GetImageProperties</a>
</td>
<td align="left" width="63%">
The <b>GetImageProperties</b> method gets an image property that is based on the content type.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551918">IPartImage::SetImageContent</a>
</td>
<td align="left" width="63%">
The <b>SetImageContent</b> method sets an image property that is based on the content type.

</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551846">IPartBase</a>
 

 

