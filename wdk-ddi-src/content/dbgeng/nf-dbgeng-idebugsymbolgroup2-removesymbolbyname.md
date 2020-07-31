---
UID: NF:dbgeng.IDebugSymbolGroup2.RemoveSymbolByName
title: IDebugSymbolGroup2::RemoveSymbolByName (dbgeng.h)
description: The RemoveSymbolByName method removes the specified symbol from a symbol group.
old-location: debugger\removesymbolbyname.htm
tech.root: debugger
ms.assetid: 2b03f010-cc3c-48a1-b86c-df470a832c94
ms.date: 05/03/2018
keywords: ["IDebugSymbolGroup2::RemoveSymbolByName"]
ms.keywords: ComOther_894176f1-bf26-4780-b287-a97993dd6e79.xml, IDebugSymbolGroup interface [Windows Debugging],RemoveSymbolByName method, IDebugSymbolGroup2 interface [Windows Debugging],RemoveSymbolByName method, IDebugSymbolGroup2.RemoveSymbolByName, IDebugSymbolGroup2::RemoveSymbolByName, IDebugSymbolGroup::RemoveSymbolByName, RemoveSymbolByName, RemoveSymbolByName method [Windows Debugging], RemoveSymbolByName method [Windows Debugging],IDebugSymbolGroup interface, RemoveSymbolByName method [Windows Debugging],IDebugSymbolGroup2 interface, dbgeng/IDebugSymbolGroup2::RemoveSymbolByName, dbgeng/IDebugSymbolGroup::RemoveSymbolByName, debugger.removesymbolbyname
f1_keywords:
 - "dbgeng/IDebugSymbolGroup.RemoveSymbolByName"
 - "IDebugSymbolGroup.RemoveSymbolByName"
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
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
- IDebugSymbolGroup.RemoveSymbolByName
- IDebugSymbolGroup2.RemoveSymbolByName
targetos: Windows
req.typenames: 
---

# IDebugSymbolGroup2::RemoveSymbolByName


## -description


The <b>RemoveSymbolByName</b>  method removes the specified symbol from a symbol group.


## -parameters




### -param Name [in]

The name of the symbol to remove from the symbol group.


## -returns



<b>RemoveSymbolByName</b> might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>
 

This method can also return error values.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.




## -remarks



When a symbol is removed, the indexes of the symbols that remain in the symbol group might change.

For more information about symbol groups, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/scopes-and-symbol-groups">Scopes and Symbol Groups</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-addsymbol">AddSymbol</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-getsymbolname">GetSymbolName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbolgroup">IDebugSymbolGroup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbolgroup2">IDebugSymbolGroup2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-removesymbolbyindex">RemoveSymbolByIndex</a>
 

 

