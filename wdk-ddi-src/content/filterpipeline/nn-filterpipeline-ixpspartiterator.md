---
UID: NN:filterpipeline.IXpsPartIterator
title: IXpsPartIterator
author: windows-driver-content
description: The IXpsPartIterator interface is an iterator for XPS parts.
old-location: print\ixpspartiterator.htm
old-project: print
ms.assetid: 6fd51647-e7e4-4c9a-ae87-00eb3e1d3fbb
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: print.ixpspartiterator, IXpsPartIterator interface [Print Devices], IXpsPartIterator interface [Print Devices], described, IXpsPartIterator, filterpipeline/IXpsPartIterator, filterpipeline_75476300-7fcc-46a5-8a48-abde1dcd5e36.xml
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
-	IXpsPartIterator
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IXpsPartIterator interface


## -description


The <code>IXpsPartIterator</code> interface is an iterator for XPS parts.


## -members

The <b>IXpsPartIterator</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556339">IXpsPartIterator::Current</a>
</td>
<td align="left" width="63%">
The <code>Current</code> method provides the current URI and part.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556342">IXpsPartIterator::IsDone</a>
</td>
<td align="left" width="63%">
The <code>IsDone</code> method determines whether the iterator has finished  the iteration.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556346">IXpsPartIterator::Next</a>
</td>
<td align="left" width="63%">
The <code>Next</code> method advances the iterator to the next part.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556348">IXpsPartIterator::Reset</a>
</td>
<td align="left" width="63%">
The <code>Reset</code> method sets the iterator to the first element.

</td>
</tr>
</table>The <code>Current</code> method provides the current URI and part.

The <code>IsDone</code> method determines whether the iterator has finished  the iteration.

The <code>Next</code> method advances the iterator to the next part.

The <code>Reset</code> method sets the iterator to the first element.

 

