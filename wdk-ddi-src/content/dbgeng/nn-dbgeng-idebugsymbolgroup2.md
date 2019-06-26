---
UID: NN:dbgeng.IDebugSymbolGroup2
title: IDebugSymbolGroup2 (dbgeng.h)
description: IDebugSymbolGroup2 interface
old-location: debugger\idebugsymbolgroup2.htm
tech.root: debugger
ms.assetid: d702fe69-966c-4b9a-aa0e-b8376288cb79
ms.date: 05/03/2018
ms.keywords: IDebugSymbolGroup2, IDebugSymbolGroup2 interface [Windows Debugging], IDebugSymbolGroup2 interface [Windows Debugging],described, dbgeng/IDebugSymbolGroup2, debugger.idebugsymbolgroup2
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
- IDebugSymbolGroup2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbolGroup2 interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugSymbolGroup2</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbolgroup">IDebugSymbolGroup</a>. <b>IDebugSymbolGroup2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugSymbolGroup2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-addsymbolwide">AddSymbolWide</a>
</td>
<td align="left" width="63%">
Adds a symbol to a symbol group.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getsymbolentryinformation">GetSymbolEntryInformation</a>
</td>
<td align="left" width="63%">
Returns information about a symbol in a symbol group.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-getsymbolnamewide">GetSymbolNameWide</a>
</td>
<td align="left" width="63%">
Returns the name of a symbol in a symbol group.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-getsymboloffset">GetSymbolOffset</a>
</td>
<td align="left" width="63%">
Retrieves the location in the process's virtual address space of a symbol in a symbol group, if the symbol has an absolute address.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-getsymbolregister">GetSymbolRegister</a>
</td>
<td align="left" width="63%">
Returns the register that contains the value or a pointer to the value of a symbol in a symbol group.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-getsymbolsize">GetSymbolSize</a>
</td>
<td align="left" width="63%">
Returns the size of a symbol's value.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-getsymboltypename">GetSymbolTypeName</a>
</td>
<td align="left" width="63%">
Returns the name of the specified symbol's type.
(ANSI version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-getsymboltypenamewide">GetSymbolTypeNameWide</a>
</td>
<td align="left" width="63%">
Returns the name of the specified symbol's type.
(Unicode version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-getsymbolvaluetext">GetSymbolValueText</a>
</td>
<td align="left" width="63%">
Returns a string that represents the value of a symbol.
(ANSI version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-getsymbolvaluetextwide">GetSymbolValueTextWide</a>
</td>
<td align="left" width="63%">
Returns a string that represents the value of a symbol.
(Unicode version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-outputastypewide">OutputAsTypeWide</a>
</td>
<td align="left" width="63%">
Changes the type of a symbol in a symbol group. The symbol's entry is updated to represent the new type.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-removesymbolbynamewide">RemoveSymbolByNameWide</a>
</td>
<td align="left" width="63%">
Removes the specified symbol from a symbol group.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-writesymbolwide">WriteSymbolWide</a>
</td>
<td align="left" width="63%">
Sets the value of the specified symbol.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbolgroup">IDebugSymbolGroup</a>
 

 

