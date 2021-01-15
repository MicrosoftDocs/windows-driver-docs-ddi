---
UID: NF:dbgeng.IDebugSymbols3.GetSymbolModuleWide
title: IDebugSymbols3::GetSymbolModuleWide (dbgeng.h)
description: The GetSymbolModuleWide method returns the base address of module which contains the specified symbol.
old-location: debugger\getsymbolmodulewide.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::GetSymbolModuleWide"]
ms.keywords: GetSymbolModuleWide, GetSymbolModuleWide method [Windows Debugging], GetSymbolModuleWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetSymbolModuleWide method, IDebugSymbols3.GetSymbolModuleWide, IDebugSymbols3::GetSymbolModuleWide, dbgeng/IDebugSymbols3::GetSymbolModuleWide, debugger.getsymbolmodulewide
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
 - IDebugSymbols3::GetSymbolModuleWide
 - dbgeng/IDebugSymbols3::GetSymbolModuleWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbols3::GetSymbolModuleWide
---

# IDebugSymbols3::GetSymbolModuleWide


## -description

The <b>GetSymbolModuleWide</b> method returns the base address of module which contains the specified symbol.

## -parameters

### -param Symbol 

[in]
Specifies the name of the symbol to look up.  See the Remarks section for details of the syntax of this name.

### -param Base 

[out]
Receives the location in the target's memory address space of the base of the module.  For more information, see <a href="/windows-hardware/drivers/debugger/modules">Modules</a>.

## -returns

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The symbol or module could not be found.

</td>
</tr>
</table>

## -remarks

The string <i>Symbol</i> must contain an exclamation point ( <b>!</b> ).  If <i>Symbol</i> is a module-qualified symbol name (for example, <b>mymodules!main</b>) or if the module name is omitted (for example, <b>!main</b>), the engine will search for this symbol and return the module in which it is found.  If <i>Symbol</i> contains just a module name (for example, <b>mymodule!</b>) the engine returns the first module with this module name.

For more information about symbols, see <a href="/windows-hardware/drivers/debugger/symbols4">Symbols</a>.

