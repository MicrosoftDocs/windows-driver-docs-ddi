---
UID: NN:filterpipeline.IPartImage
title: IPartImage
author: windows-driver-content
description: The IPartImage interface is the abstraction for images in an XPS document.
old-location: print\ipartimage.htm
old-project: print
ms.assetid: 7bb39a5b-7519-47a6-82ca-440942ae2c84
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IXpsPartIterator, IXpsPartIterator::Reset, Reset
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
req.alt-api: IPartImage
req.alt-loc: filterpipeline.h
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
req.typenames: EXpsFontRestriction
---

# IPartImage interface



## -description
The <b>IPartImage</b> interface is the abstraction for images in an XPS document.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPartImage</b> interface inherits from <a href="..\filterpipeline\nn-filterpipeline-ipartbase.md">IPartBase</a>. <b>IPartImage</b> also has these types of members:

The <b>IPartImage</b> interface has these methods.

The <b>GetImageProperties</b> method gets an image property that is based on the content type.

The <b>SetImageContent</b> method sets an image property that is based on the content type.

 


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
</table>The <b>GetImageProperties</b> method gets an image property that is based on the content type.

The <b>SetImageContent</b> method sets an image property that is based on the content type.

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\filterpipeline\nn-filterpipeline-ipartbase.md">IPartBase</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPartImage interface%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

