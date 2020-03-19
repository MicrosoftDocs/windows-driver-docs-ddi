---
UID: NF:dbgeng.IDebugSymbols.SetSymbolOptions
title: IDebugSymbols::SetSymbolOptions (dbgeng.h)
description: The SetSymbolOptions method changes the engine's global symbol options.
old-location: debugger\setsymboloptions.htm
tech.root: debugger
ms.assetid: 06cfae40-eb32-4f9b-b7ad-266cb12f4a32
ms.date: 05/03/2018
keywords: ["IDebugSymbols::SetSymbolOptions"]
ms.keywords: IDebugSymbols interface [Windows Debugging],SetSymbolOptions method, IDebugSymbols.SetSymbolOptions, IDebugSymbols2 interface [Windows Debugging],SetSymbolOptions method, IDebugSymbols2::SetSymbolOptions, IDebugSymbols3 interface [Windows Debugging],SetSymbolOptions method, IDebugSymbols3::SetSymbolOptions, IDebugSymbols::SetSymbolOptions, IDebugSymbols_56cfcd8d-304b-4433-beab-2fc3e58a54a4.xml, SetSymbolOptions, SetSymbolOptions method [Windows Debugging], SetSymbolOptions method [Windows Debugging],IDebugSymbols interface, SetSymbolOptions method [Windows Debugging],IDebugSymbols2 interface, SetSymbolOptions method [Windows Debugging],IDebugSymbols3 interface, dbgeng/IDebugSymbols2::SetSymbolOptions, dbgeng/IDebugSymbols3::SetSymbolOptions, dbgeng/IDebugSymbols::SetSymbolOptions, debugger.setsymboloptions
f1_keywords:
 - "dbgeng/IDebugSymbols.SetSymbolOptions"
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
- IDebugSymbols.SetSymbolOptions
- IDebugSymbols2.SetSymbolOptions
- IDebugSymbols3.SetSymbolOptions
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols::SetSymbolOptions


## -description


The <b>SetSymbolOptions</b> method changes the engine's global symbol options.


## -parameters




### -param Options [in]

Specifies the new symbol options.  <i>Options</i> is a bit-set; it will replace the existing symbol options.  For a description of the bit flags, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/symbol-options">Setting Symbol Options</a>.


## -returns



This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
 




## -remarks



This method will set the engine's global symbol options to those specified in <i>Options</i>.  Unlike <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-addsymboloptions">AddSymbolOptions</a>, any symbol options not in the bit-set <i>Options</i> will be removed.

After the symbol options have been changed, for each client the engine sends out notification to that client's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugeventcallbacks">IDebugEventCallbacks</a> by passing the DEBUG_CES_SYMBOL_OPTIONS flag to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-changesymbolstate">IDebugEventCallbacks::ChangeSymbolState</a> method.

For more information about symbols, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/symbols4">Symbols</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-addsymboloptions">AddSymbolOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getsymboloptions">GetSymbolOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols">IDebugSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-removesymboloptions">RemoveSymbolOptions</a>
 

 

