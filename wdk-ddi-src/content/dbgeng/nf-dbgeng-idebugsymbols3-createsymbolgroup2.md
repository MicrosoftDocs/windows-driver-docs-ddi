---
UID: NF:dbgeng.IDebugSymbols3.CreateSymbolGroup2
title: IDebugSymbols3::CreateSymbolGroup2 (dbgeng.h)
description: The CreateSymbolGroup2 method creates a new symbol group.
old-location: debugger\createsymbolgroup2.htm
tech.root: debugger
ms.assetid: 42ddf77a-14c8-4d6a-98a2-b0c67836990d
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::CreateSymbolGroup2"]
ms.keywords: CreateSymbolGroup2, CreateSymbolGroup2 method [Windows Debugging], CreateSymbolGroup2 method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],CreateSymbolGroup2 method, IDebugSymbols3.CreateSymbolGroup2, IDebugSymbols3::CreateSymbolGroup2, dbgeng/IDebugSymbols3::CreateSymbolGroup2, debugger.createsymbolgroup2
f1_keywords:
 - "dbgeng/IDebugSymbols3.CreateSymbolGroup2"
 - "IDebugSymbols3.CreateSymbolGroup2"
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
- Dbgeng.h
api_name:
- IDebugSymbols3.CreateSymbolGroup2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::CreateSymbolGroup2


## -description


The <b>CreateSymbolGroup2</b>  method creates a new symbol group.


## -parameters




### -param Group [out]

Receives an interface pointer for the new <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbolgroup">IDebugSymbolGroup</a> object.


## -returns



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
 

This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.




## -remarks



The newly created symbol group is empty; it does not contain any <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/symbols4">symbols</a>.  Symbols may be added to the symbol group using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-addsymbol">IDebugSymbolGroup::AddSymbol</a>.

References to the returned object are managed like other COM objects, using the <b>IUnknown::AddRef</b> and <b>IUnknown::Release</b> methods.  In particular, the <b>IUnknown::Release</b> method must be called when the returned object is no longer needed.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-client-objects">Using Client Objects</a> for more information about using COM interfaces in the Debugger Engine API.

For more information about symbol groups, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/scopes-and-symbol-groups">Scopes and Symbol Groups</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbolgroup">IDebugSymbolGroup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-addsymbol">IDebugSymbolGroup::AddSymbol</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
 

 

