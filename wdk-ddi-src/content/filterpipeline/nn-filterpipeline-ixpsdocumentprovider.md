---
UID: NN:filterpipeline.IXpsDocumentProvider
title: IXpsDocumentProvider
author: windows-driver-content
description: The IxpsDocumentProvider interface provides interfaces to consume parts of a document.
old-location: print\ixpsdocumentprovider.htm
old-project: print
ms.assetid: e1fac90f-5c21-4857-a52f-04c5366d7b18
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: print.ixpsdocumentprovider, IXpsDocumentProvider interface [Print Devices], IXpsDocumentProvider interface [Print Devices], described, IXpsDocumentProvider, filterpipeline/IXpsDocumentProvider, filterpipeline_5c7b0fb9-f191-47c7-b0fc-96371c21f993.xml
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
req.lib: filterpipeline.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	filterpipeline.h
apiname:
-	IXpsDocumentProvider
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IXpsDocumentProvider interface


## -description


The <code>IxpsDocumentProvider</code> interface provides interfaces to consume parts of a document.
<div class="alert"><b>Note</b>    The XPS print filter pipeline does not preserve digital signatures or story fragments. You may be able to work around this by using stream filters.</div><div> </div>

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

 

