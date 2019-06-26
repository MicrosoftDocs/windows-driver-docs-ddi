---
UID: NN:dbgeng.IDebugSymbols4
title: IDebugSymbols4 (dbgeng.h)
description: This interface supports determination of the symbol of an inline frame.
old-location: debugger\idebugsymbols4.htm
tech.root: debugger
ms.assetid: BE2734B5-1E67-4E38-B4DF-0C353BFB1F0B
ms.date: 05/03/2018
ms.keywords: IDebugSymbols4, IDebugSymbols4 interface [Windows Debugging], IDebugSymbols4 interface [Windows Debugging],described, dbgeng/IDebugSymbols4, debugger.idebugsymbols4
ms.topic: interface
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
- Dbgeng.h
api_name:
- IDebugSymbols4
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols4 interface


## -description


This interface supports determination of the symbol of an inline frame.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugSymbols4</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IDebugSymbols4</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugSymbols4</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols4-getlinebyinlinecontext">GetLineByInlineContext</a>
</td>
<td align="left" width="63%">
Gets a line by inline context.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols4-getlinebyinlinecontextwide">GetLineByInlineContextWide</a>
</td>
<td align="left" width="63%">
Gets a line by inline context.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols4-getnamebyinlinecontext">GetNameByInlineContext</a>
</td>
<td align="left" width="63%">
Gets a name by inline context.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols4-getnamebyinlinecontextwide">GetNameByInlineContextWide</a>
</td>
<td align="left" width="63%">
Gets a name by inline context.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols4-getscopeex">GetScopeEx</a>
</td>
<td align="left" width="63%">
Gets the scope as an extended frame structure. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols4-outputsymbolbyinlinecontext">OutputSymbolByInlineContext</a>
</td>
<td align="left" width="63%">
Specifies an output symbol by using an inline context.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols4-setscopeex">SetScopeEx</a>
</td>
<td align="left" width="63%">
Sets the scope as an extended frame structure. 

</td>
</tr>
</table> 

