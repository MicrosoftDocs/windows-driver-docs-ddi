---
UID: NN:filterpipeline.IXpsDocument
title: IXpsDocument
author: windows-driver-content
description: The IXpsDocument interface represents the root of an XPS document.
old-location: print\ixpsdocument.htm
old-project: print
ms.assetid: 1d4a9ad3-6ac1-44c3-9ddd-0dc5f996d70d
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
req.alt-api: IXpsDocument
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

# IXpsDocument interface



## -description
The <code>IXpsDocument</code> interface represents the root of an XPS document.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IXpsDocument</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IXpsDocument</b> also has these types of members:

The <b>IXpsDocument</b> interface has these methods.

The <code>GetThumbnail</code> method gets the document thumbnail object. 

The <code>SetThumbnail</code> method removes the current thumbnail object from the document and inserts a new one.

 


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
</table>The <code>GetThumbnail</code> method gets the document thumbnail object. 

The <code>SetThumbnail</code> method removes the current thumbnail object from the document and inserts a new one.

 


## -remarks
