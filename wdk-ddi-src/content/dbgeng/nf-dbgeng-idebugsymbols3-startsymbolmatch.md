---
UID: NF:dbgeng.IDebugSymbols3.StartSymbolMatch
title: IDebugSymbols3::StartSymbolMatch (dbgeng.h)
description: The StartSymbolMatch method initializes a search for symbols whose names match a given pattern.
old-location: debugger\startsymbolmatch.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::StartSymbolMatch"]
ms.keywords: IDebugSymbols interface [Windows Debugging],StartSymbolMatch method, IDebugSymbols2 interface [Windows Debugging],StartSymbolMatch method, IDebugSymbols2::StartSymbolMatch, IDebugSymbols3 interface [Windows Debugging],StartSymbolMatch method, IDebugSymbols3.StartSymbolMatch, IDebugSymbols3::StartSymbolMatch, IDebugSymbols::StartSymbolMatch, IDebugSymbols_4b000f13-0dc1-4a2c-8de3-3bf5384172c3.xml, StartSymbolMatch, StartSymbolMatch method [Windows Debugging], StartSymbolMatch method [Windows Debugging],IDebugSymbols interface, StartSymbolMatch method [Windows Debugging],IDebugSymbols2 interface, StartSymbolMatch method [Windows Debugging],IDebugSymbols3 interface, dbgeng/IDebugSymbols2::StartSymbolMatch, dbgeng/IDebugSymbols3::StartSymbolMatch, dbgeng/IDebugSymbols::StartSymbolMatch, debugger.startsymbolmatch
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
 - IDebugSymbols3::StartSymbolMatch
 - dbgeng/IDebugSymbols3::StartSymbolMatch
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbols3::StartSymbolMatch
---

# IDebugSymbols3::StartSymbolMatch


## -description

The <b>StartSymbolMatch</b> method initializes a search for symbols whose names match a given pattern.

## -parameters

### -param Pattern 

[in]
Specifies the pattern for which to search.  The search will return all symbols whose names match this pattern.  For details of the syntax of the pattern, see <a href="/windows-hardware/drivers/debugger/symbol-syntax-and-symbol-matching">Symbol Syntax and Symbol Matching</a> and <a href="/windows-hardware/drivers/debugger/string-wildcard-syntax">String Wildcard Syntax</a>.

### -param Handle 

[out]
Receives the handle identifying the search.  This handle can be passed to <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getnextsymbolmatch">GetNextSymbolMatch</a> and <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-endsymbolmatch">EndSymbolMatch</a>.

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
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The specified module was not found.

</td>
</tr>
</table>

## -remarks

This method initializes a symbol search.  The results of the search can be obtained by repeated calls to <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getnextsymbolmatch">GetNextSymbolMatch</a>.  When all the desired results have been found, use <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-endsymbolmatch">EndSymbolMatch</a> to release resources the engine holds for the search.

For more information about symbols, see <a href="/windows-hardware/drivers/debugger/symbols4">Symbols</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-endsymbolmatch">EndSymbolMatch</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getnextsymbolmatch">GetNextSymbolMatch</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols">IDebugSymbols</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>

