---
UID: NF:dbgeng.IDebugSymbolGroup2.RemoveSymbolByNameWide
title: IDebugSymbolGroup2::RemoveSymbolByNameWide (dbgeng.h)
description: The RemoveSymbolByNameWide method removes the specified symbol from a symbol group.
old-location: debugger\removesymbolbynamewide.htm
tech.root: debugger
ms.assetid: 12261b88-681e-4623-b5af-abaae756e3e1
ms.date: 05/03/2018
ms.keywords: IDebugSymbolGroup2 interface [Windows Debugging],RemoveSymbolByNameWide method, IDebugSymbolGroup2.RemoveSymbolByNameWide, IDebugSymbolGroup2::RemoveSymbolByNameWide, RemoveSymbolByNameWide, RemoveSymbolByNameWide method [Windows Debugging], RemoveSymbolByNameWide method [Windows Debugging],IDebugSymbolGroup2 interface, dbgeng/IDebugSymbolGroup2::RemoveSymbolByNameWide, debugger.removesymbolbynamewide
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugSymbolGroup2.RemoveSymbolByNameWide"
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
- IDebugSymbolGroup2.RemoveSymbolByNameWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbolGroup2::RemoveSymbolByNameWide


## -description


The  <b>RemoveSymbolByNameWide</b> method removes the specified symbol from a symbol group.


## -parameters




### -param Name [in]

The name of the symbol to remove from the symbol group.


## -returns



<b>RemoveSymbolByNameWide</b> might return one of the following values:

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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-addsymbol">AddSymbol</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-getsymbolname">GetSymbolName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbolgroup2">IDebugSymbolGroup2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-removesymbolbyindex">RemoveSymbolByIndex</a>
 

 

