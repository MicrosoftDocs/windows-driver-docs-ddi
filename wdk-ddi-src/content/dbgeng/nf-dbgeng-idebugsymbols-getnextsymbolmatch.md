---
UID: NF:dbgeng.IDebugSymbols.GetNextSymbolMatch
title: IDebugSymbols::GetNextSymbolMatch (dbgeng.h)
description: The GetNextSymbolMatch method returns the next symbol found in a symbol search. This method belongs to the IDebugSymbols interface.
old-location: debugger\getnextsymbolmatch.htm
tech.root: debugger
ms.date: 02/06/2022
keywords: ["IDebugSymbols::GetNextSymbolMatch"]
ms.keywords: GetNextSymbolMatch, GetNextSymbolMatch method [Windows Debugging], GetNextSymbolMatch method [Windows Debugging],IDebugSymbols interface, GetNextSymbolMatch method [Windows Debugging],IDebugSymbols2 interface, GetNextSymbolMatch method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],GetNextSymbolMatch method, IDebugSymbols.GetNextSymbolMatch, IDebugSymbols2 interface [Windows Debugging],GetNextSymbolMatch method, IDebugSymbols2::GetNextSymbolMatch, IDebugSymbols3 interface [Windows Debugging],GetNextSymbolMatch method, IDebugSymbols3::GetNextSymbolMatch, IDebugSymbols::GetNextSymbolMatch, IDebugSymbols_9918b348-5b29-4b38-849e-3a36414b773d.xml, dbgeng/IDebugSymbols2::GetNextSymbolMatch, dbgeng/IDebugSymbols3::GetNextSymbolMatch, dbgeng/IDebugSymbols::GetNextSymbolMatch, debugger.getnextsymbolmatch
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
 - IDebugSymbols::GetNextSymbolMatch
 - dbgeng/IDebugSymbols::GetNextSymbolMatch
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbols::GetNextSymbolMatch
---

# IDebugSymbols::GetNextSymbolMatch


## -description

The <b>GetNextSymbolMatch</b>  method returns the next symbol found in a symbol search.

## -parameters

### -param Handle [in]


Specifies the handle returned by <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-startsymbolmatch">StartSymbolMatch</a> when the search was initialized.

### -param Buffer [out, optional]


Receives the name of the symbol.  If <i>Buffer</i> is <b>NULL</b>, the same symbol will be returned again next time one of these methods are called (with the same handle); this can be used to determine the size of the name of the symbol.

### -param BufferSize [in]


Specifies the size in characters of the buffer. This size includes the space for the '\0' terminating character.

### -param MatchSize [out, optional]


Receives the size in characters of the name of the symbol. This size includes the space for the '\0' terminating character. If <i>MatchSize</i> is <b>NULL</b>, this information is not returned.

### -param Offset [out, optional]


Receives the location in the target's virtual address space of the symbol.  If <i>Offset</i> is <b>NULL</b>, this information is not returned.

## -returns

This method may also return other error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

The search must first be initialized by <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-startsymbolmatch">StartSymbolMatch</a>.  Once all the desired symbols have been found, <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-endsymbolmatch">EndSymbolMatch</a> can be used to release the resources the engine holds for the search.

For more information about symbols, see <a href="/windows-hardware/drivers/debugger/symbols4">Symbols</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-endsymbolmatch">EndSymbolMatch</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols">IDebugSymbols</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-startsymbolmatch">StartSymbolMatch</a>

