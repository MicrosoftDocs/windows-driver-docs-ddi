---
UID: NN:filterpipeline.IFixedDocument
title: IFixedDocument
author: windows-driver-content
description: The IFixedDocument interface represents a fixed document for an XPS document sequence.
old-location: print\ifixeddocument.htm
old-project: print
ms.assetid: 3f9f64a1-8681-4b70-8cdc-7c944912f767
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
req.alt-api: IFixedDocument
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

# IFixedDocument interface



## -description
The <b>IFixedDocument</b> interface represents a fixed document for an XPS document sequence.  An XPS fixed document sequence will have one or more fixed documents in it.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IFixedDocument</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IFixedDocument</b> also has these types of members:

The <b>IFixedDocument</b> interface has these methods.

The <b>GetPrintTicket</b> method gets the print ticket object for the fixed document.

The <b>GetUri</b> method gets the URI of the fixed document.

The <b>SetPrintTicket</b> method inserts a print ticket into the fixed document.

 


## -members
The <b>IFixedDocument</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550992">IFixedDocument::GetPrintTicket</a>
</td>
<td align="left" width="63%">
The <b>GetPrintTicket</b> method gets the print ticket object for the fixed document.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551002">IFixedDocument::GetUri</a>
</td>
<td align="left" width="63%">
The <b>GetUri</b> method gets the URI of the fixed document.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551012">IFixedDocument::SetPrintTicket</a>
</td>
<td align="left" width="63%">
The <b>SetPrintTicket</b> method inserts a print ticket into the fixed document.

</td>
</tr>
</table>The <b>GetPrintTicket</b> method gets the print ticket object for the fixed document.

The <b>GetUri</b> method gets the URI of the fixed document.

The <b>SetPrintTicket</b> method inserts a print ticket into the fixed document.

 


## -remarks
