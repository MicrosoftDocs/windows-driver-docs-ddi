---
UID: NN:dbgeng.IDebugSymbolGroup
title: IDebugSymbolGroup (dbgeng.h)
description: IDebugSymbolGroup interface
old-location: debugger\idebugsymbolgroup.htm
tech.root: debugger
ms.assetid: dd629e4a-938e-4db6-b0f3-6dd12a431486
ms.date: 05/03/2018
ms.keywords: ComOther_f174a794-e2c2-4d0a-912e-b3de6327ef19.xml, IDebugSymbolGroup, IDebugSymbolGroup interface [Windows Debugging], IDebugSymbolGroup interface [Windows Debugging],described, dbgeng/IDebugSymbolGroup, debugger.idebugsymbolgroup
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
- dbgeng.h
api_name:
- IDebugSymbolGroup
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbolGroup interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugSymbolGroup</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IDebugSymbolGroup</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugSymbolGroup</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-addsymbol">AddSymbol</a>
</td>
<td align="left" width="63%">
Adds a symbol to a symbol group.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-expandsymbol">ExpandSymbol</a>
</td>
<td align="left" width="63%">
Adds or removes the children of a symbol from a symbol group.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-getnumbersymbols">GetNumberSymbols</a>
</td>
<td align="left" width="63%">
 Returns the number of symbols that are contained in a symbol group.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-getsymbolname">GetSymbolName</a>
</td>
<td align="left" width="63%">
Returns the name of a symbol in a symbol group.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-getsymbolparameters">GetSymbolParameters</a>
</td>
<td align="left" width="63%">
Returns the symbol parameters that describe the specified symbols in a symbol group.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-outputastype">OutputAsType</a>
</td>
<td align="left" width="63%">
Changes the type of a symbol in a symbol group. The symbol's entry is updated to represent the new type. 


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-outputsymbols">OutputSymbols</a>
</td>
<td align="left" width="63%">
Prints the specified symbols to the debugger console.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-removesymbolbyindex">RemoveSymbolByIndex</a>
</td>
<td align="left" width="63%">
Removes the specified symbol from a symbol group.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-removesymbolbyname">RemoveSymbolByName</a>
</td>
<td align="left" width="63%">
 Removes the specified symbol from a symbol group.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-writesymbol">WriteSymbol</a>
</td>
<td align="left" width="63%">
Sets the value of the specified symbol.


</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbolgroup2">IDebugSymbolGroup2</a>
 

 

