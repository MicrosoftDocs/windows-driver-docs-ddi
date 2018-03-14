---
UID: NN:filterpipeline.IFixedDocument
title: IFixedDocument
author: windows-driver-content
description: The IFixedDocument interface represents a fixed document for an XPS document sequence.
old-location: print\ifixeddocument.htm
old-project: print
ms.assetid: 3f9f64a1-8681-4b70-8cdc-7c944912f767
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IFixedDocument, IFixedDocument interface [Print Devices], IFixedDocument interface [Print Devices], described, filterpipeline/IFixedDocument, filterpipeline_f295da8e-1444-40c4-8ecf-e3aadc1d324f.xml, print.ifixeddocument
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
-	IFixedDocument
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IFixedDocument interface


## -description


The <b>IFixedDocument</b> interface represents a fixed document for an XPS document sequence.  An XPS fixed document sequence will have one or more fixed documents in it.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IFixedDocument</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IFixedDocument</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

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
</table> 

