---
UID: NN:filterpipeline.IXpsDocumentProvider
title: IXpsDocumentProvider
author: windows-driver-content
description: The IxpsDocumentProvider interface provides interfaces to consume parts of a document.
old-location: print\ixpsdocumentprovider.htm
old-project: print
ms.assetid: e1fac90f-5c21-4857-a52f-04c5366d7b18
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
req.alt-api: IXpsDocumentProvider
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

# IXpsDocumentProvider interface



## -description
The <code>IxpsDocumentProvider</code> interface provides interfaces to consume parts of a document.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IXpsDocumentProvider</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IXpsDocumentProvider</b> also has these types of members:

The <b>IXpsDocumentProvider</b> interface has these methods.

The <code>GetXpsPart</code> method retrieves several objects that make up an XPS document.

 


## -members
The <b>IXpsDocumentProvider</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556324">IXpsDocumentProvider::GetXpsPart</a>
</td>
<td align="left" width="63%">
The <code>GetXpsPart</code> method retrieves several objects that make up an XPS document.

</td>
</tr>
</table>The <code>GetXpsPart</code> method retrieves several objects that make up an XPS document.

 


## -remarks
