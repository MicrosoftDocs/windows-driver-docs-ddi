---
UID: NF:dbgeng.IDebugSymbols3.CreateSymbolGroup
title: IDebugSymbols3::CreateSymbolGroup (dbgeng.h)
description: The CreateSymbolGroup method creates a new symbol group.
old-location: debugger\createsymbolgroup.htm
tech.root: debugger
ms.assetid: f55aa290-5e57-48d8-9454-370c494bbd65
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::CreateSymbolGroup"]
ms.keywords: CreateSymbolGroup, CreateSymbolGroup method [Windows Debugging], CreateSymbolGroup method [Windows Debugging],IDebugSymbols interface, CreateSymbolGroup method [Windows Debugging],IDebugSymbols2 interface, CreateSymbolGroup method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],CreateSymbolGroup method, IDebugSymbols2 interface [Windows Debugging],CreateSymbolGroup method, IDebugSymbols2::CreateSymbolGroup, IDebugSymbols3 interface [Windows Debugging],CreateSymbolGroup method, IDebugSymbols3.CreateSymbolGroup, IDebugSymbols3::CreateSymbolGroup, IDebugSymbols::CreateSymbolGroup, IDebugSymbols_fe8b31b2-0c5c-4dde-9d60-a353893e3f65.xml, dbgeng/IDebugSymbols2::CreateSymbolGroup, dbgeng/IDebugSymbols3::CreateSymbolGroup, dbgeng/IDebugSymbols::CreateSymbolGroup, debugger.createsymbolgroup
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugSymbols3::CreateSymbolGroup
 - dbgeng/IDebugSymbols3::CreateSymbolGroup
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Dbgeng.h
api_name:
 - IDebugSymbols.CreateSymbolGroup
 - IDebugSymbols2.CreateSymbolGroup
 - IDebugSymbols3.CreateSymbolGroup
---

# IDebugSymbols3::CreateSymbolGroup


## -description

The <b>CreateSymbolGroup</b>  method creates a new symbol group.

## -parameters

### -param Group 

[out]
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



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols">IDebugSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>

