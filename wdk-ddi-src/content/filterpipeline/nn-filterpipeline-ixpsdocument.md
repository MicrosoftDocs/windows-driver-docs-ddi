---
UID: NN:filterpipeline.IXpsDocument
title: IXpsDocument (filterpipeline.h)
description: The IXpsDocument interface represents the root of an XPS document.
old-location: print\ixpsdocument.htm
tech.root: print
ms.assetid: 1d4a9ad3-6ac1-44c3-9ddd-0dc5f996d70d
ms.date: 04/20/2018
ms.keywords: IXpsDocument, IXpsDocument interface [Print Devices], IXpsDocument interface [Print Devices],described, filterpipeline/IXpsDocument, filterpipeline_d2db5467-7b2d-439c-8ad1-3ffb607a3167.xml, print.ixpsdocument
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
- IXpsDocument
product:
- Windows
targetos: Windows
req.typenames: 
---

# IXpsDocument interface


## -description


The <code>IXpsDocument</code> interface represents the root of an XPS document.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IXpsDocument</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IXpsDocument</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IXpsDocument</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556328">IXpsDocument::GetThumbnail</a>
</td>
<td align="left" width="63%">
The <code>GetThumbnail</code> method gets the document thumbnail object. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556330">IXpsDocument::SetThumbnail</a>
</td>
<td align="left" width="63%">
The <code>SetThumbnail</code> method removes the current thumbnail object from the document and inserts a new one.

</td>
</tr>
</table> 

