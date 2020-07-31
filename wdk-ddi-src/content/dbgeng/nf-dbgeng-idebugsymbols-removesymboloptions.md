---
UID: NF:dbgeng.IDebugSymbols.RemoveSymbolOptions
title: IDebugSymbols::RemoveSymbolOptions (dbgeng.h)
description: The RemoveSymbolOptions method turns off some of the engine's global symbol options.
old-location: debugger\removesymboloptions.htm
tech.root: debugger
ms.assetid: a4e1f579-8056-4e2b-9b90-735c3414abbd
ms.date: 05/03/2018
keywords: ["IDebugSymbols::RemoveSymbolOptions"]
ms.keywords: IDebugSymbols interface [Windows Debugging],RemoveSymbolOptions method, IDebugSymbols.RemoveSymbolOptions, IDebugSymbols2 interface [Windows Debugging],RemoveSymbolOptions method, IDebugSymbols2::RemoveSymbolOptions, IDebugSymbols3 interface [Windows Debugging],RemoveSymbolOptions method, IDebugSymbols3::RemoveSymbolOptions, IDebugSymbols::RemoveSymbolOptions, IDebugSymbols_a6b53bc6-23e5-4dae-b3b8-09330e91caba.xml, RemoveSymbolOptions, RemoveSymbolOptions method [Windows Debugging], RemoveSymbolOptions method [Windows Debugging],IDebugSymbols interface, RemoveSymbolOptions method [Windows Debugging],IDebugSymbols2 interface, RemoveSymbolOptions method [Windows Debugging],IDebugSymbols3 interface, dbgeng/IDebugSymbols2::RemoveSymbolOptions, dbgeng/IDebugSymbols3::RemoveSymbolOptions, dbgeng/IDebugSymbols::RemoveSymbolOptions, debugger.removesymboloptions
f1_keywords:
 - "dbgeng/IDebugSymbols.RemoveSymbolOptions"
 - "IDebugSymbols.RemoveSymbolOptions"
req.header: dbgeng.h
req.include-header: Dbgeng.h, Dbghelp.h
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
- IDebugSymbols.RemoveSymbolOptions
- IDebugSymbols2.RemoveSymbolOptions
- IDebugSymbols3.RemoveSymbolOptions
targetos: Windows
req.typenames: 
---

# IDebugSymbols::RemoveSymbolOptions


## -description


The <b>RemoveSymbolOptions</b> method turns off some of the engine's global symbol options.


## -parameters




### -param Options [in]

Specifies the symbol options to turn off.  <i>Options</i> is a bit-set; the new value of the symbol options will equal the old value AND NOT the value of <i>Options</i>.  For a description of the bit flags, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/symbol-options">Setting Symbol Options</a>.


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



After the symbol options have been changed, for each client the engine sends out notification to that client's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugeventcallbacks">IDebugEventCallbacks</a> by it passing the DEBUG_CES_SYMBOL_OPTIONS flag to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-changesymbolstate">IDebugEventCallbacks::ChangeSymbolState</a> method.

For more information about symbols, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/symbols4">Symbols</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-addsymboloptions">AddSymbolOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getsymboloptions">GetSymbolOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols">IDebugSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-setsymboloptions">SetSymbolOptions</a>
 

 

