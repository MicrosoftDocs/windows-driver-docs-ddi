---
UID: NF:dbgeng.IDebugSymbols.Reload
title: IDebugSymbols::Reload (dbgeng.h)
description: The Reload method deletes the engine's symbol information for the specified module and reload these symbols as needed.
old-location: debugger\reload.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSymbols::Reload"]
ms.keywords: IDebugSymbols interface [Windows Debugging],Reload method, IDebugSymbols.Reload, IDebugSymbols2 interface [Windows Debugging],Reload method, IDebugSymbols2::Reload, IDebugSymbols3 interface [Windows Debugging],Reload method, IDebugSymbols3::Reload, IDebugSymbols::Reload, IDebugSymbols_ec5df701-b081-45c4-b2e4-10c101ce69a4.xml, Reload, Reload method [Windows Debugging], Reload method [Windows Debugging],IDebugSymbols interface, Reload method [Windows Debugging],IDebugSymbols2 interface, Reload method [Windows Debugging],IDebugSymbols3 interface, dbgeng/IDebugSymbols2::Reload, dbgeng/IDebugSymbols3::Reload, dbgeng/IDebugSymbols::Reload, debugger.reload
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
 - IDebugSymbols::Reload
 - dbgeng/IDebugSymbols::Reload
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbols.Reload
 - IDebugSymbols2.Reload
 - IDebugSymbols3.Reload
---

# IDebugSymbols::Reload


## -description

The <b>Reload</b>  method deletes the engine's symbol information for the specified module and reload these symbols as needed.

## -parameters

### -param Module 

[in]
Specifies the module to reload.

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
The method was successful

</td>
</tr>
</table>
 

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

## -remarks

This method behaves the same way as the debugger command <b>.reload</b>.  The <i>Module</i> parameter is treated the same way as the arguments to <b>.reload</b>.  For example, setting the <i>Module</i> parameter to "/u ntdll.dll" has the same effect as the command <b>.reload /u ntdll.dll</b>.

For more information about symbols, see <a href="/windows-hardware/drivers/debugger/symbols4">Symbols</a>.

## -see-also

<a href="/windows-hardware/drivers/debugger/-reload--reload-module-">.reload (Reload Module)</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols">IDebugSymbols</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
