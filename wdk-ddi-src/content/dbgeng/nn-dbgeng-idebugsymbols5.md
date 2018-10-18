---
UID: NN:dbgeng.IDebugSymbols5
title: IDebugSymbols5
author: windows-driver-content
description: This interface supports using index values for the current frame.
old-location: debugger\idebugsymbols5.htm
tech.root: debugger
ms.assetid: 0D239C0E-96C8-49F9-BDFD-182F3F7C3976
ms.date: 5/3/2018
ms.keywords: IDebugSymbols5, IDebugSymbols5 interface [Windows Debugging], IDebugSymbols5 interface [Windows Debugging],described, dbgeng/IDebugSymbols5, debugger.idebugsymbols5
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Dbgeng.h
api_name:
-	IDebugSymbols5
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols5 interface


## -description


This interface supports using index values for the current frame. 


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugSymbols5</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IDebugSymbols5</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugSymbols5</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/0D8198BB-583F-4828-8131-61EB17621F32">GetCurrentScopeFrameIndexEx</a>
</td>
<td align="left" width="63%">
Gets the index of the current frame.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/E0638C55-4160-48A5-9378-6AA9AAC8DC36">SetScopeFrameByIndexEx</a>
</td>
<td align="left" width="63%">
Sets the current frame by using an index.

</td>
</tr>
</table> 

