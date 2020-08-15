---
UID: NF:dbgeng.IDebugSymbols3.GetSymbolOptions
title: IDebugSymbols3::GetSymbolOptions (dbgeng.h)
description: The GetSymbolOptions method returns the engine's global symbol options.
old-location: debugger\getsymboloptions.htm
tech.root: debugger
ms.assetid: a9da40fa-59b7-4d2b-978f-1785a51eeaed
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::GetSymbolOptions"]
ms.keywords: GetSymbolOptions, GetSymbolOptions method [Windows Debugging], GetSymbolOptions method [Windows Debugging],IDebugSymbols interface, GetSymbolOptions method [Windows Debugging],IDebugSymbols2 interface, GetSymbolOptions method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],GetSymbolOptions method, IDebugSymbols2 interface [Windows Debugging],GetSymbolOptions method, IDebugSymbols2::GetSymbolOptions, IDebugSymbols3 interface [Windows Debugging],GetSymbolOptions method, IDebugSymbols3.GetSymbolOptions, IDebugSymbols3::GetSymbolOptions, IDebugSymbols::GetSymbolOptions, IDebugSymbols_70c05823-d1a1-4769-8584-e191255c4deb.xml, dbgeng/IDebugSymbols2::GetSymbolOptions, dbgeng/IDebugSymbols3::GetSymbolOptions, dbgeng/IDebugSymbols::GetSymbolOptions, debugger.getsymboloptions
f1_keywords:
 - "dbgeng/IDebugSymbols.GetSymbolOptions"
 - "IDebugSymbols.GetSymbolOptions"
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
- IDebugSymbols.GetSymbolOptions
- IDebugSymbols2.GetSymbolOptions
- IDebugSymbols3.GetSymbolOptions
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetSymbolOptions


## -description


The <b>GetSymbolOptions</b> method returns the engine's global symbol options.


## -parameters




### -param Options 
[out]
Receives the symbol options bit-set.  For a description of the bit flags, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/symbol-options">Setting Symbol Options</a>.


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



For more information about symbols, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/symbols4">Symbols</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-addsymboloptions">AddSymbolOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols">IDebugSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-removesymboloptions">RemoveSymbolOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-setsymboloptions">SetSymbolOptions</a>
 

 

