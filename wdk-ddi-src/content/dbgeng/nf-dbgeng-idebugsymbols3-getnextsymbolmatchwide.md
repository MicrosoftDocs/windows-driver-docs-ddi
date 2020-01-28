---
UID: NF:dbgeng.IDebugSymbols3.GetNextSymbolMatchWide
title: IDebugSymbols3::GetNextSymbolMatchWide (dbgeng.h)
description: The GetNextSymbolMatchWide method returns the next symbol found in a symbol search.
old-location: debugger\getnextsymbolmatchwide.htm
tech.root: debugger
ms.assetid: 0400ff8c-a6d5-4fbf-b2fb-eb9fd7aabd7e
ms.date: 05/03/2018
ms.keywords: GetNextSymbolMatchWide, GetNextSymbolMatchWide method [Windows Debugging], GetNextSymbolMatchWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetNextSymbolMatchWide method, IDebugSymbols3.GetNextSymbolMatchWide, IDebugSymbols3::GetNextSymbolMatchWide, dbgeng/IDebugSymbols3::GetNextSymbolMatchWide, debugger.getnextsymbolmatchwide
f1_keywords:
 - "dbgeng/IDebugSymbols3.GetNextSymbolMatchWide"
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
- IDebugSymbols3.GetNextSymbolMatchWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetNextSymbolMatchWide


## -description


The <b>GetNextSymbolMatchWide</b>  method returns the next symbol found in a symbol search.


## -parameters




### -param Handle [in]

Specifies the handle returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-startsymbolmatch">StartSymbolMatch</a> when the search was initialized.


### -param Buffer [out, optional]

Receives the name of the symbol.  If <i>Buffer</i> is <b>NULL</b>, the same symbol will be returned again next time one of these methods are called (with the same handle); this can be used to determine the size of the name of the symbol.


### -param BufferSize [in]

Specifies the size in characters of the buffer.


### -param MatchSize [out, optional]

Receives the size in characters of the name of the symbol.  If <i>MatchSize</i> is <b>NULL</b>, this information is not returned.


### -param Offset [out, optional]

Receives the location in the target's virtual address space of the symbol.  If <i>Offset</i> is <b>NULL</b>, this information is not returned.


## -returns



This method may also return other error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The size of the buffer was too small for the name of the symbol, or <i>Buffer</i> was <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
No more symbols were found matching the pattern.

</td>
</tr>
</table>
 




## -remarks



The search must first be initialized by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-startsymbolmatch">StartSymbolMatch</a>.  Once all the desired symbols have been found, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-endsymbolmatch">EndSymbolMatch</a> can be used to release the resources the engine holds for the search.

For more information about symbols, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/symbols4">Symbols</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-endsymbolmatch">EndSymbolMatch</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-startsymbolmatch">StartSymbolMatch</a>
 

 

