---
UID: NN:filterpipeline.IXpsDocumentConsumer
title: IXpsDocumentConsumer
author: windows-driver-content
description: A filter uses the IXpsDocumentConsumer interface when it generates XPS content for the pipeline to consume.
old-location: print\ixpsdocumentconsumer.htm
old-project: print
ms.assetid: 98e603e6-2786-4bc8-ad8a-0e91b0d444d8
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
req.alt-api: IXpsDocumentConsumer
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

# IXpsDocumentConsumer interface



## -description
A filter uses the <code>IXpsDocumentConsumer</code> interface when it generates XPS content for the pipeline to consume. 



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IXpsDocumentConsumer</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IXpsDocumentConsumer</b> also has these types of members:

The <b>IXpsDocumentConsumer</b> interface has these methods.

The <code>CloseSender</code> method tells the Pipeline Manager that the filter is done sending XPS parts.

The <code>GetNewEmptyPart</code> method creates a new XPS part.

The <code>SendFixedDocument</code> method sends a fixed document object to the pipeline.

The <b>SendFixedDocumentSequence</b> method sends a fixed document sequence to the pipeline.

The <code>SendFixedPage</code> method sends a fixed page of an XPS document to the pipeline.

The <code>SendXpsDocument</code> method sends an XPS document to the pipeline. 

The <code>SendXpsUnknown</code> method sends an XPS document part that cannot be identified to the filter pipeline.

 


## -members
The <b>IXpsDocumentConsumer</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556293">IXpsDocumentConsumer::CloseSender</a>
</td>
<td align="left" width="63%">
The <code>CloseSender</code> method tells the Pipeline Manager that the filter is done sending XPS parts.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556295">IXpsDocumentConsumer::GetNewEmptyPart</a>
</td>
<td align="left" width="63%">
The <code>GetNewEmptyPart</code> method creates a new XPS part.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556300">IXpsDocumentConsumer::SendFixedDocument</a>
</td>
<td align="left" width="63%">
The <code>SendFixedDocument</code> method sends a fixed document object to the pipeline.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556303">IXpsDocumentConsumer::SendFixedDocumentSequence</a>
</td>
<td align="left" width="63%">
The <b>SendFixedDocumentSequence</b> method sends a fixed document sequence to the pipeline.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556309">IXpsDocumentConsumer::SendFixedPage</a>
</td>
<td align="left" width="63%">
The <code>SendFixedPage</code> method sends a fixed page of an XPS document to the pipeline.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556312">IXpsDocumentConsumer::SendXpsDocument</a>
</td>
<td align="left" width="63%">
The <code>SendXpsDocument</code> method sends an XPS document to the pipeline. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556314">IXpsDocumentConsumer::SendXpsUnknown</a>
</td>
<td align="left" width="63%">
The <code>SendXpsUnknown</code> method sends an XPS document part that cannot be identified to the filter pipeline.

</td>
</tr>
</table>The <code>CloseSender</code> method tells the Pipeline Manager that the filter is done sending XPS parts.

The <code>GetNewEmptyPart</code> method creates a new XPS part.

The <code>SendFixedDocument</code> method sends a fixed document object to the pipeline.

The <b>SendFixedDocumentSequence</b> method sends a fixed document sequence to the pipeline.

The <code>SendFixedPage</code> method sends a fixed page of an XPS document to the pipeline.

The <code>SendXpsDocument</code> method sends an XPS document to the pipeline. 

The <code>SendXpsUnknown</code> method sends an XPS document part that cannot be identified to the filter pipeline.

 


## -remarks
